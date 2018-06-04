---
title: 'How to: Activate a Workflow from a Workflow Type'
TOCTitle: 'How to: Activate a Workflow from a Workflow Type'
ms:assetid: bb54e1e7-e062-4150-bffa-eb2a846c1cfd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc618309(v=AX.60)
ms:contentKeyID: 35249951
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Activate a Workflow from a Workflow Type 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, workflow can be activated by using a workflow type, configuration ID, or sequence number. This procedure describes how to use a workflow type to activate a workflow.

When you activate a workflow by using the workflow type, Microsoft Dynamics AX workflow will:

1.  Get a list of all configuration versions based on the workflow type.

2.  Remove configuration versions that are not active.

3.  Evaluate workflow conditions for each active configuration version.
    
      - If only one configuration version meets the workflow conditions, that configuration version is activated.
    
      - If more than one configuration version meets the workflow conditions, then an exception is thrown.
    
      - If there are no workflow conditions, the default configuration version is activated.

To activate a workflow by using a workflow type, follow these steps:

1.  Create an action menu item.

2.  Bind the action menu item to the workflow type.

3.  Create and implement a class to activate the workflow.

4.  Associate the action menu item with the class.

### To create an action menu item and bind it to the workflow type

1.  In the AOT, expand the **Menu Items** node.

2.  Right-click the **Action** node, and then click **New Menu Item**. An action menu item displays under the **Menu Items** node.

3.  Right-click the new action menu item and then click **Properties**.

4.  In the **Properties** sheet, set the following properties.
    
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
    <td><p>The name that is used to reference the menu item action, for example, SubmitToWorkflow.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>The label used for the action menu item in the user interface. For example, enter Activate as a name for a button that the user will click to activate the workflow.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p>Set to Class. Use this value to implement the class for this action item.</p></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, expand the **Workflow** node, and then expand the **Workflow Types** node.

6.  Right-click the workflow type that you want to bind an action menu item to and then click **Properties**.

7.  In the **Properties** sheet, set the **SubmitToWorkflowMenuItem** property to the action menu item that you created.

After an action menu item is created, the next step is to create a class that implements the action menu item.

### To create a class to activate a workflow using a workflow type

1.  In the AOT, right-click the **Classes** node, and then click **New Class**. A new class displays under the **Classes** node.

2.  Right-click the new class, click **Rename**, and then enter a name.

3.  Right-click the new class and then click **New Method**. The **Editor** window opens.

4.  In the **Editor** window, insert the code for the action to take to activate the workflow by using a workflow type.
    

    > [!NOTE]
    > <P>See the code example in the following example that contains a static main method implementation for an issue handling workflow.</P>



5.  In the AOT, expand the **Menu Items** node.

6.  Expand the **Action** node, and then select the action menu item to implement the class created in the previous procedure.

7.  In the **Properties** sheet, set the **Object** property to the name of the class to activate the workflow.

## Example

The following code example shows a sample implementation of the static main method on a class that activates a workflow by using a workflow type. For more information, see [Workflow::activateFromWorkflowType Method](https://msdn.microsoft.com/en-us/library/gg812416\(v=ax.60\)). In this example, the workflow type is used to enable issue handling in a module.

This code example uses the IssueStateChangeManager class to change the state of the business document as the workflow progresses. You can also manage the state change that results from workflow activation directly in the SubmitToWorkflow class that you create for the SubmitToWorkflowMenuItem property setting in the workflow type.

When the workflow is activated, this code will open a dialog box to add user comments.

    public static void main(Args args)
    {
        // Variable declaration.
        recId _recId = args.record().RecId;
        WorkflowCorrelationId _workflowCorrelationId;
        workflowTypeName _workflowTypeName = workflowtypestr("IssueHandling");
        // Initial note is the information that users enter when they
        // submit the document for workflow.
        WorkflowComment _initialNote = "";
        WorkflowSubmitDialog workflowSubmitDialog;
     
        // Opens the submit to workflow dialog.
        workflowSubmitDialog = WorkflowSubmitDialog::construct(_args.caller().getActiveWorkflowConfiguration());
        workflowSubmitDialog.run();
     
        if (workflowSubmitDialog.parmIsClosedOK())
        {
            _recId = _args.record().RecId;
            
            // Get comments from the submit to workflow dialog.
            _initialNote = workflowSubmitDialog.parmWorkflowComment();
     
            try
            { 
                // Activate the workflow.
     
                _workflowCorrelationId = Workflow::activateFromWorkflowType(_workflowTypeName, _recId, _initialNote, NoYes::No);
                
                // Set the workflow state to Submitted.
                IssueStateChangeManager::submit(args.record());
            
            }
     
            catch(exception::Error)
            {
                // ToDo Enter your code for the error action taken here.
            }
        }
    }

## See also

[How to: Create a New Workflow Type](how-to-create-a-new-workflow-type.md)

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

[Workflow::activateFromWorkflowType Method](https://msdn.microsoft.com/en-us/library/gg812416\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

