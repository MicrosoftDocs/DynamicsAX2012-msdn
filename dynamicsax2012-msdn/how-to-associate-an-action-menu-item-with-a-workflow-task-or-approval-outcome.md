---
title: 'How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome'
TOCTitle: 'How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome'
ms:assetid: 8500d3c4-22af-4375-a77d-cd941c7320cc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc602158(v=AX.60)
ms:contentKeyID: 35246169
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you create a task or approval in a Microsoft Dynamics AX workflow, you must create and add an action menu item. The end-user can start the task or approval by clicking the button for the action menu item. The following procedures describe how to add an action menu item to a task or approval outcome, and then implement a class for the action menu item.


> [!NOTE]
> <P>Use the same procedures when you add an action item to a web client task or approval outcome in the <STRONG>Actions</STRONG> node in the <STRONG>Web Menu Items</STRONG> node of the Application Object Tree (AOT).</P>



For more information about how to add a display menu item that displays the form for a task or approval, see [How to: Associate a Display Menu item with a Workflow Task or Approval](how-to-associate-a-display-menu-item-with-a-workflow-task-or-approval.md).

Before you begin this procedure, you must create a task or approval outcome that you need to add to an action menu item. For more information, see [How to: Create a Workflow Task](how-to-create-a-workflow-task.md) and [How to: Create a Workflow Approval](how-to-create-a-workflow-approval.md).

### To bind an action menu item to a task outcome

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
    <td><p>The name that is used to reference the menu item action, for example, TaskComplete.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>The label used for the action menu item in the user interface. For example, enter Complete to identify that the workflow is activated.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p>Set to <strong>Class</strong>. Use this value to implement the class for this action item.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Object</strong></p></td>
    <td><p>Set to WorkflowWorkItemActionManager (for Enterprise Portal, set to EPWorkflowWorkItemActionManager) to use the default workflow action manager. Optionally, implement a custom class.</p>
    
    > [!note]  
    > <P>The <strong>Resubmit</strong> and <strong>Submit</strong> action menu items will require a custom class as this action affects the state of your document.</P>
    
    </td>
    </tr>
    <tr class="odd">
    <td><p><strong>ConfigurationKey</strong></p></td>
    <td><p>The configuration key assigned to this menu item.</p></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, expand the **Workflow** node, expand the **Tasks** node, and then expand the **Outcomes** node.

6.  Right-click the task outcome that you want to bind an action menu item to and then click **Properties**.

7.  In the **Properties** sheet, set the **ActionMenuItem** property to the task action menu item that you created in step 4.

After an action menu item for a task or approval outcome is created, you can implement the menu item using the workflow work item action manager or create a customized class that implements the action menu item. For more information, see the [WorkflowWorkItemActionManager Class](https://msdn.microsoft.com/en-us/library/gg815458\(v=ax.60\)).

### To implement a class for an action menu item

1.  In the AOT, right-click the **Classes** node, and then click **New Class**. A new class displays under the **Classes** node.

2.  Right-click the new class, click **Rename**, and then enter a name.

3.  Right-click the new class and then click **New Method**. The **Editor** window opens.

4.  In the **Editor** window, insert the code for the action to take when the action menu item is selected in the user interface.
    
    The following example shows the submit action when the purchase requisition workflow is submitted. The workflow configuration is activated by calling the [Workflow::activateFromWorkflowType Method](https://msdn.microsoft.com/en-us/library/gg812416\(v=ax.60\)) method on the [Workflow Class](https://msdn.microsoft.com/en-us/library/gg812434\(v=ax.60\)) class.
    ```X++  
        void submit()
        {
            NoYes activatingFromWeb;
        
            // If we have a workflow control context, we are being activated from EP.
            activatingFromWeb = this.parmWorkflowControlContext() == null ? NoYes::No : NoYes::Yes;
        
            ttsbegin;
            if (PurchReqWFStatusTransitionHelper::setPurchReqTable2InReview(purchReqTable.RecId))
            {
                Workflow::activateFromWorkflowType(this.parmWorkflowTemplateName(),
                                                   purchReqTable.RecId,
                                                   this.parmWorkflowComment(),
                                                   activatingFromWeb,
                                                   DirPersonUser::worker2UserId(purchReqTable.Originator));
            }
            ttscommit;
        }
    ```
5.  In the AOT, expand the **Menu Items** node.

6.  Expand the **Action** node, and then select the action menu item that will use the class that you created in step 4.

7.  In the **Properties** sheet, set the **Object** property to the name of the class that you implemented. When the user selects the action menu item in the user interface, the method in this class will be run.

After your task or approval outcomes have action menu items associated with them, you are ready to add the task or approval to the workflow type. For more information, see [How to: Add a Task, Automated Task, or Approval to a Workflow Type](how-to-add-a-task-automated-task-or-approval-to-a-workflow-type.md).

## See also

[Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md)

[How to: Associate a Display Menu item with a Workflow Task or Approval](how-to-associate-a-display-menu-item-with-a-workflow-task-or-approval.md)

[Workflow Approval Checklist](workflow-approval-checklist.md)

[Workflow Task Checklist](workflow-task-checklist.md)

[Creating a Workflow Type](creating-a-workflow-type.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

