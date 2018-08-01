---
title: Workflow Task Checklist
TOCTitle: Workflow Task Checklist
ms:assetid: d6599f9b-4de7-4860-9134-7f9e6bd8ef35
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc620991(v=AX.60)
ms:contentKeyID: 35252053
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Task Checklist [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following topic shows how you can create a task for a rich client or web client in a Microsoft Dynamics AX workflow. Before you create tasks, you must have a workflow type. For more information, see [Creating a Workflow Type](creating-a-workflow-type.md).

## Task Checklist for a Rich Client

1.  Create a task in the Application Object Tree (AOT). For more information, see [How to: Create a Workflow Task](how-to-create-a-workflow-task.md).

2.  Create task event handler classes for the **StartedEventHandler** and **CanceledEventHandler** property settings and then bind the event handlers to the task. For more information, see [How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md).

3.  Set the **Document** property for the task to match the workflow type **Document** property setting. For more information, see [How to: Create a New Workflow Type](how-to-create-a-new-workflow-type.md).

4.  Create a display menu item and then bind the menu item to the **DocumentMenuItem** property for the task. For more information, see [How to: Associate a Display Menu item with a Workflow Task or Approval](how-to-associate-a-display-menu-item-with-a-workflow-task-or-approval.md).

5.  Create classes for **Resubmit** and **Delegate**. Bind the classes to the action menu items that you will create in the next step. For more information, see [Classes in X++](classes-in-x.md).
    

    > [!NOTE]
    > <P>You can use the <A href="https://msdn.microsoft.com/en-us/library/gg815458(v=ax.60)">WorkflowWorkItemActionManager Class</A> for the <STRONG>Delegate</STRONG> action menu item. Optionally, create your own class to handle the task delegate action.</P>



6.  Create action menu items for the task **ResubmitMenuItem** and **DelegateMenuItem** properties, and then bind the actions to the task. For more information, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).

7.  Create a task outcome for Complete, and then optionally, create additional outcomes. For more information, see [How to: Create a Workflow Task](how-to-create-a-workflow-task.md).
    

    > [!NOTE]
    > <P>Each task must have one outcome of type Complete.</P>



8.  Create classes for each task outcome. Bind the classes to the action menu items that you will create in the next step. For more information, see [Classes in X++](classes-in-x.md).
    

    > [!NOTE]
    > <P>You can use the <A href="https://msdn.microsoft.com/en-us/library/gg815458(v=ax.60)">WorkflowWorkItemActionManager Class</A> for the task action menu items. Optionally, create your own class to handle task outcomes.</P>



9.  Create an action menu item for each task outcome created in the previous step. Bind the actions to the outcomes in the task **Outcomes** node. For more information, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).

10. Set the workflow task outcome **Enabled** property to No for task outcome types that are not used.

## Task Checklist for a Web Client

1.  Create a task in the Application Object Tree (AOT). For more information, see [How to: Create a Workflow Task](how-to-create-a-workflow-task.md).

2.  Create task event handler classes for the **StartedEventHandler** and **CanceledEventHandler** property settings and then bind the event handlers to the task. For more information, see [How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md).

3.  Set the **Document** property for the task to match the workflow type **Document** property setting. For more information, see [How to: Create a New Workflow Type](how-to-create-a-new-workflow-type.md).

4.  In the **Web Menu Items** node, create a **URLs** object and then bind the web menu item to the **DocumentWebMenuItem** property for the task. For more information, see [How to: Associate a Display Menu item with a Workflow Task or Approval](how-to-associate-a-display-menu-item-with-a-workflow-task-or-approval.md).

5.  Create classes for **Resubmit** and **Delegate**. Bind the classes to the web menu items that you will create in the next step. For more information, see [Classes in X++](classes-in-x.md).
    

    > [!NOTE]
    > <P>You can use the <A href="https://msdn.microsoft.com/en-us/library/gg766887(v=ax.60)">EPWorkflowWorkItemActionManager Class</A> for the <STRONG>Delegate</STRONG> action menu item. Optionally, create your own class to handle the task delegate.</P>



6.  In the **Web Menu Items** node, create two actions menu items for the task **ResubmitMenuItem** and **DelegateMenuItem** properties. Bind the actions to the task. For more information, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).

7.  Create a task outcome of type Complete, and then optionally, create additional outcomes. For more information, see [How to: Create a Workflow Task](how-to-create-a-workflow-task.md).
    

    > [!NOTE]
    > <P>Each task must have one outcome of type Complete and an action menu item for the task work item button to display in the user interface</P>



8.  Create classes for each task outcome. Bind the classes to the actions menu items that you will create in the next step. For more information, see [Classes in X++](classes-in-x.md).
    

    > [!NOTE]
    > <P>You can use the <A href="https://msdn.microsoft.com/en-us/library/gg766887(v=ax.60)">EPWorkflowWorkItemActionManager Class</A> for the task actions menu items. Optionally, create your own class to handle task outcomes.</P>



9.  In the **Web Menu Items** node, create an action menu item for each task outcome created in the previous step. Bind the actions to the outcomes in the task **Outcomes** node. For more information, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).

10. Set the workflow task outcome Enabled property to No for task outcome types that are not used.

### ![Cc620991.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc620991.collapse_all(en-us,AX.60).gif")Next Steps

After you create a task, you can bind it to the **Supported Elements** node of the workflow type in the AOT. For more information, see [How to: Add a Task, Automated Task, or Approval to a Workflow Type](how-to-add-a-task-automated-task-or-approval-to-a-workflow-type.md).

## See also

[How to: Create a Workflow Task](how-to-create-a-workflow-task.md)

[How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md)

[How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

