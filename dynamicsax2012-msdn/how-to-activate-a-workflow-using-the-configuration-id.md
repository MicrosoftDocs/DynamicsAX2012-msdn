---
title: 'How to: Activate a Workflow using the Configuration ID'
TOCTitle: 'How to: Activate a Workflow using the Configuration ID'
ms:assetid: 59279568-0cfd-4b80-ae0b-c041ece518df
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc554429(v=AX.60)
ms:contentKeyID: 35244341
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Activate a Workflow using the Configuration ID 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, workflow can be activated by using a workflow type, configuration ID, or sequence number. When you activate a workflow by using the configuration ID, the specified workflow configuration version that is stored in the database is used to create a new workflow instance. You should activate a workflow using this procedure when there is more than one version of the same configuration and you want a specific version to run. These procedures describe how to use a configuration ID to activate a workflow.

To activate a workflow by using a configuration ID, follow these steps:

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
    <td><p>The label used for the action menu item in the user interface. For example, enter Activate to identify a button that will activate the workflow.</p></td>
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

### To create a class to activate a workflow using a configuration ID

1.  In the AOT, right-click the **Classes** node, and then click **New Class**. A new class displays under the **Classes** node.

2.  Right-click the new class, click **Rename**, and then enter a name.

3.  Right-click the new class and then click **New Method**. The **Editor** window opens.

4.  In the **Editor** window, insert the code for the action to take to activate the workflow by using a configuration ID.
    

    > [!NOTE]
    > <P>See the code example in the following example that contains a static main method implementation for an issue handling workflow.</P>



5.  In the AOT, expand the **Menu Items** node.

6.  Expand the **Action** node, and then select the action menu item to implement the class created in the procedure earlier.

7.  In the **Properties** sheet, set the **Object** property to the name of the class to activate the workflow.

## Example

The following code example shows a sample implementation of the static main method on class that activates a workflow by using a specified configuration ID. For more information, see [Workflow::activateFromWorkflowConfigurationId Method](https://msdn.microsoft.com/en-us/library/gg812414\(v=ax.60\)). In this example, the workflow configuration is used to enable the issue handling workflow in a module.

This code example uses the IssueStateChangeManager class to change the state of the business document as the workflow progresses. You can also manage the state change that results from workflow activation directly in the SubmitToWorkflow class that you create for the SubmitToWorkflowMenuItem property setting in the workflow type.

When the workflow is activated, the following code will open a dialog box to add user comments.

    public static void main(Args args)
    {
        // Variable declaration.
        recId _recId = args.record().RecId;
        WorkflowCorrelationId workflowCorrelationId;
        WorkflowConfiguration wfConfig;
    
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
     
                wfConfig = args.caller().getActiveWorkflowConfiguration();
    
                // Activate the workflow.
                workflowCorrelationId = Workflow::activateFromWorkflowConfigurationId(wfConfig.parmConfigurationId(), _recId, _initialNote, NoYes::No);
    
                // Set the workflow state to Submitted.
                IssueStateChangeManager::submit(args.record());
     
                ttscommit;
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

[Workflow::activateFromWorkflowConfigurationId Method](https://msdn.microsoft.com/en-us/library/gg812414\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

