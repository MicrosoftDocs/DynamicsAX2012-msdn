---
title: 'Walkthrough: Creating a Workflow Type'
TOCTitle: 'Walkthrough: Creating a Workflow Type'
ms:assetid: e89957f3-7211-421f-85d7-63a34c90acc8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc641259(v=AX.60)
ms:contentKeyID: 35253227
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Workflow Type [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you define a workflow by creating a workflow type to base the workflow on. In this walkthrough, you will create a workflow type in the AOT that you can add approvals and tasks to.

A workflow type defines information about the following:

  - Which document is being used with the workflow. The workflow document exposes calculated fields and identifies the query that exposes data fields for the workflow.

  - Tasks, automated tasks, and approvals that can be configured by the end user.

  - Workflow categories used for assigning a workflow type to a specific module.

  - Menu items and event handlers.

This walkthrough illustrates the following tasks:

  - Creating a query for a workflow.

  - Creating a workflow category.

  - Creating a workflow type in the AOT.

  - Adding code to the SubmitManager class.

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - A license file that has access to the Development workspace

### To Create a Query for a Workflow

1.  In the AOT, right-click the **Queries** node, and then select **New Query**. A query group displays under the **Queries** node.

2.  Right-click the new query, click **Rename**, and then enter **MyQuery**.

3.  Expand the new query, right-click the **Data Sources** node, and then click **New Data Source**. A data source group displays under the **Data Sources** node.

4.  Right-click the new data source group and then click **Properties**.

5.  In the **Properties** sheet, set the **Table** property to **CustTable**.

6.  Expand the CusTable\_1 data source, and select the **Fields** node. In the **Properties** sheet, set the **Dynamic** property to **Yes**.
    

    > [!NOTE]
    > <P>By setting the <STRONG>Dynamic</STRONG> property to Yes, all data fields in the CustTable table are exposed for workflow conditions. To remove data fields, set the <STRONG>Dynamic</STRONG> property on the <STRONG>Fields</STRONG> node of the data source to <STRONG>No</STRONG>. Expand the <STRONG>Fields</STRONG> node, right-click a field, and then click <STRONG>Delete</STRONG>. If the query is not saved, the <STRONG>Delete</STRONG> command is not available.</P>



7.  In the AOT, right-click **MyQuery**, and then click **Save**.

After a Microsoft Dynamics AX query is created, you must decide which category the workflow will be part of. We recommend that you choose an existing workflow category. If no category is appropriate, you can create your own.

### To Create a Workflow Category

1.  In the AOT, expand the **Workflow** node.

2.  Right-click the **Workflow Categories** node, and then select **New Workflow Category**. A new workflow category group displays under the **Workflow Categories** node.

3.  Right-click the new workflow category and then click **Properties**.

4.  In the **Properties** sheet, set the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>MyWorkflowCategory</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Module</strong></p></td>
    <td><p>Customer</p></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, right-click **MyWorkflowCategory**, and then click **Save**.

After a workflow category is created, you are ready to create the workflow type.

### To Create a Workflow Type in the AOT

1.  In the AOT, expand the **Workflow** node.

2.  Right-click the **Workflow Types** node, and then click **Add-Ins** \> **Workflow type wizard**. The **Workflow wizard** is displayed. This wizard will help you create a new workflow type.

3.  Click **Next**.

4.  Set the following values for the wizard.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Value</p></th>
    <th><p>Input</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Enter MyWorkflowType.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Category</strong></p></td>
    <td><p>Choose MyWorkflowCategory, which is the category that you created.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Query</strong></p></td>
    <td><p>Choose MyQuery, which is the query that you created.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Document menu item</strong></p></td>
    <td><p>Choose CustTable, which points to the main form for displaying customer data.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document web menu item</strong></p></td>
    <td><p>Choose EPCustTableInfo, which points to the main page for displaying customer data in Enterprise Portal.</p></td>
    </tr>
    </tbody>
    </table>


5.  Click **Both** to generate menu items for both the Microsoft Dynamics AX client and Enterprise Portal.

6.  Click **Next**. A list of all of the resources that will be created for the workflow type is displayed.

7.  Click **Finish** to create the resources. The wizard will create classes, menu items, web menu items, the workflow type, and a project that contains all of the items.

8.  A dialog box will be displayed that indicates the status. Click **OK**. The project that contains the workflow type resources is displayed.

After the workflow type is created, you will add code for the workflow events. However, to simplify this walkthrough, you will not add code to any of the event handlers.

To enable end-users to submit a workflow document for approval, you will have to add code that is run when the user clicks **Submit** in Microsoft Dynamics AX. The main method in the SubmitManager class that was created by the **Workflow wizard** will run. This code will display a message in the user interface that indicates that the document was submitted to workflow.

### To Add Code to the SubmitManager Class

1.  In the AOT, expand the **Classes** node.

2.  Locate the **MyWorkflowTypeSubmitManager** class. This was the class created by the **Workflow wizard**.

3.  Expand the **MyWorkflowTypeSubmitManager** class, and then double-click the main method. The **Editor** window opens.

4.  In the **Editor** window, insert the following code.
    
        public static void main(Args args)
        {
            // Variable declaration.
            recId _recId = args.record().RecId;
            WorkflowCorrelationId _workflowCorrelationId;
            // Hardcoded type name
            workflowTypeName _workflowTypeName = workFlowTypeStr("MyWorkflowType");
            // Initial note is the information that users enter when they
            // submit the document for workflow.
            WorkflowComment _initialNote = "";
            WorkflowSubmitDialog workflowSubmitDialog;
        
            // Opens the submit to workflow dialog.
            workflowSubmitDialog = WorkflowSubmitDialog::construct(args.caller().getActiveWorkflowConfiguration());
            workflowSubmitDialog.run();
        
            if (workflowSubmitDialog.parmIsClosedOK())
            {
                   _recId = args.record().RecId;
                // Get comments from the submit to workflow dialog.
                _initialNote = workflowSubmitDialog.parmWorkflowComment();
        
                try
                {
                    ttsbegin;
        
                    // Activate the workflow.
                    _workflowCorrelationId = Workflow::activateFromWorkflowType(_workflowTypeName, _recId, _initialNote, NoYes::No);
        
                    // Send an Infolog message.
                    info("Submitted to workflow.");
        
                    ttscommit;
                }
        
                catch(exception::Error)
                {
                    info("Error on workflow activation.");
                }
            }
        }

5.  Close the **Editor** window and then click **Yes** to save changes.

6.  Any time that you create or modify workflow code, you must regenerate the CIL code. In the AOT, right-click **AOT**, click **Add-Ins**, and then select **Incremental CIL generation from X++**.

After **MySubmitToWorkflowClass** is created, you can create an action menu item to bind this class to.

## Next Steps

You have now created a workflow type based on the customer table. To use the customer table form for a workflow, you must enable the form for workflow and then create a workflow configuration. For more information, see [Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md).

## See also

[Handling Workflow Events](handling-workflow-events.md)

[Activating a Workflow](activating-a-workflow.md)

[Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

[Walkthrough: Adding an Automated Task to a Workflow](walkthrough-adding-an-automated-task-to-a-workflow.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

