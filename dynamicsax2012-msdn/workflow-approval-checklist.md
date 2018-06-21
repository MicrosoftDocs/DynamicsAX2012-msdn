---
title: Workflow Approval Checklist
TOCTitle: Workflow Approval Checklist
ms:assetid: b5e2c0ec-68b8-4047-88fc-d0ff6b77a371
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc636485(v=AX.60)
ms:contentKeyID: 35249814
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Approval Checklist [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following topic shows how you can create an approval for a rich client or web client in a Microsoft Dynamics AX workflow. Before you can create approvals, you must have a workflow type. For more information, see [Creating a Workflow Type](creating-a-workflow-type.md).

## Approval Checklist for a Rich Client

1.  Create an approval in the Application Object Tree (AOT). For more information, see, [How to: Create a Workflow Approval](how-to-create-a-workflow-approval.md).

2.  Create approval event handler classes for the **StartedEventHandler** and **CanceledEventHandler** property settings and then bind the event handlers to the approval. For more information, see [How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md).

3.  Set the **Document** property for the workflow approval to match the workflow type **Document** property setting. For more information, see [How to: Create a New Workflow Type](how-to-create-a-new-workflow-type.md).

4.  Create a display menu item and then bind the menu item to the **DocumentMenuItem** property for the approval. For more information, see [How to: Associate a Display Menu item with a Workflow Task or Approval](how-to-associate-a-display-menu-item-with-a-workflow-task-or-approval.md).

5.  Create menu item classes for **Resubmit** and **Delegate**. Bind the classes to the action menu items that you will create in the next step. For more information, see [Classes in X++](classes-in-x.md).
    

    > [!NOTE]
    > <P>You can optionally use the <A href="https://msdn.microsoft.com/en-us/library/gg815458(v=ax.60)">WorkflowWorkItemActionManager Class</A> for the <STRONG>Delegate</STRONG> action menu item. Optionally, create your own class to handle the approval delegate action.</P>



6.  Create action menu items for the approval **ResubmitMenuItem** and **DelegateMenuItem** properties and then bind the actions to the approval. For more information, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).

7.  Create classes for each approval outcome. Bind the classes to the action menu items that you will create in the next step. For more information, see [Classes in X++](classes-in-x.md).
    

    > [!NOTE]
    > <P>You can use the <A href="https://msdn.microsoft.com/en-us/library/gg815458(v=ax.60)">WorkflowWorkItemActionManager Class</A> for the approval action menu items. Optionally, create your own class to handle approval outcomes.</P>



8.  Create an action menu item for each approval outcome created in the previous step. Bind the actions to the approval in the approval **Outcomes** node. For more information, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).
    

    > [!NOTE]
    > <P>Each approval must have one outcome of type <STRONG>Complete</STRONG>.</P>



9.  Set the workflow approval outcome **Enabled** property to No for approval outcome types that are not used.

## Approval Checklist for a Web Client

1.  Create an approval in the Application Object Tree (AOT). For more information, see, [How to: Create a Workflow Approval](how-to-create-a-workflow-approval.md).

2.  Create approval event handler classes for **StartedEventHandler** and **CanceledEventHandler** and then bind the event handlers to the approval. For more information, see [How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md).

3.  Set the **Document** property for the workflow approval to match the workflow type **Document** property setting. For more information, see [How to: Create a New Workflow Type](how-to-create-a-new-workflow-type.md).

4.  In the **Web Menu Items** node, create a **URLs** object and then bind the web menu item to the **DocumentWebMenuItem** property for the approval. For more information, see [How to: Associate a Display Menu item with a Workflow Task or Approval](how-to-associate-a-display-menu-item-with-a-workflow-task-or-approval.md).

5.  Create classes for **Resubmit** and **Delegate**. Bind the classes to the **ResubmitWebMenuItem** and **DelegateWebMenuItem** actions menu items that you will create in the next step. For more information, see [Classes in X++](classes-in-x.md).
    

    > [!NOTE]
    > <P>You can use the <A href="https://msdn.microsoft.com/en-us/library/gg766887(v=ax.60)">EPWorkflowWorkItemActionManager Class</A> for the <STRONG>Delegate</STRONG> actions menu item. Optionally, create your own class to handle the approval delegate action.</P>



6.  In the **Web Menu Items** node, create two actions menu items for **ResubmitWebMenuItem** and **DelegateWebMenuItem** properties and then bind the actions to the approval. For more information, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).

7.  Create classes for each approval outcome. Bind the classes to the actions menu items that you will create in the next step. For more information, see [Classes in X++](classes-in-x.md).
    

    > [!NOTE]
    > <P>You can use the <A href="https://msdn.microsoft.com/en-us/library/gg766887(v=ax.60)">EPWorkflowWorkItemActionManager Class</A> for the approval actions menu items. Optionally, create your own class to handle approval outcomes.</P>



8.  In the **Web Menu Items** node, create actions menu items for approval outcome class created in the previous step. Bind the actions to the ActionWebMenuItem property of the approval in the **Outcomes** node. For more information, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).
    

    > [!NOTE]
    > <P>Each approval must have one outcome of type <STRONG>Complete</STRONG> and an actions menu item for the approval work item button to display in the user interface.</P>



9.  Set the workflow approval outcome **Enabled** property to No for approval outcome types that are not used.

### ![Cc636485.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc636485.collapse_all(en-us,AX.60).gif")Next Steps

After you create an approval, you can bind it to the **Supported Elements** node of the workflow type in the AOT. For more information, see [Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md).

## See also

[How to: Create a Workflow Approval](how-to-create-a-workflow-approval.md)

[Workflow Approval State Transitions](workflow-approval-state-transitions.md)

[How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

