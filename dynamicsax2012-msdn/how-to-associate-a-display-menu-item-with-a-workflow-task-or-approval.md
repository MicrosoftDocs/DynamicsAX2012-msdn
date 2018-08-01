---
title: 'How to: Associate a Display Menu item with a Workflow Task or Approval'
TOCTitle: 'How to: Associate a Display Menu item with a Workflow Task or Approval'
ms:assetid: 90012b7b-0a10-4e16-9967-05c2004d2a20
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc604521(v=AX.60)
ms:contentKeyID: 35247407
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Associate a Display Menu item with a Workflow Task or Approval [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you create a task or approval in a Microsoft Dynamics AX workflow, you must add a display menu item that is used to display the form for the workflow element in the application at run-time. The end-user takes action to complete the task or approval step by using the form that is displayed. The following procedures describe how to add a display menu item to a task or approval.


> [!NOTE]
> <P>Use the same procedure when you add a web client task or approval <STRONG>URLs</STRONG> menu item in the <STRONG>Web Menu Items</STRONG> node of the Application Object Tree (AOT).</P>



For more information about how to add a task or approval to an action menu item, see [How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md).

Before you begin this procedure, you must create a task or approval that you want to add a display menu item to. For more information, see [How to: Create a Workflow Task](how-to-create-a-workflow-task.md) and [How to: Create a Workflow Approval](how-to-create-a-workflow-approval.md).

### To create a display menu item and bind it to a task

1.  In the AOT, expand the **Menu Items** node.

2.  Right-click the **Display** node, and then click **New Menu Item**. A new display menu item displays under the **Display** node.

3.  Right-click the new display menu item and then click **Properties**.

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
    <td><p>The name that is used to reference the <strong>Display</strong> menu item for the task, for example, PurchReqTable.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>The label used for the display menu item used in the user interface. For example, enter Purchase Requisition to identify the form to display when the task is activated.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p>Set to Form. Use this value to set which object type is to be displayed when the task is activated.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Object</strong></p></td>
    <td><p>Set to the form that is displayed when the task is activated, for example, the <strong>PurchReqTable</strong> form.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ConfigurationKey</strong></p></td>
    <td><p>The configuration key assigned to this menu item.</p></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, expand the **Workflow** node, and then expand the **Tasks** node.

6.  Right-click the task that you want to bind a display menu item to and then click **Properties**.

7.  In the **Properties** sheet, set the **DocumentMenuItem** property to the task display menu item that you created in step 4.

After a display menu item for a task or approval, or outcome is created, you can add the task or approval to a workflow type in the **Supported Elements** node. For more information, see [How to: Add a Task, Automated Task, or Approval to a Workflow Type](how-to-add-a-task-automated-task-or-approval-to-a-workflow-type.md).

## See also

[Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md)

[How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome](how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md)

[Workflow Approval Checklist](workflow-approval-checklist.md)

[Workflow Task Checklist](workflow-task-checklist.md)

[Creating a Workflow Type](creating-a-workflow-type.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

