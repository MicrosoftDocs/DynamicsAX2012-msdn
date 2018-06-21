---
title: 'How to: Create a Workflow Approval'
TOCTitle: 'How to: Create a Workflow Approval'
ms:assetid: 3742cf13-965f-4a2e-8046-33f3fa4a6793
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc596847(v=AX.60)
ms:contentKeyID: 35242029
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Workflow Approval 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use workflow approvals to track the status of a workflow document that has fixed workflow outcomes types such as Approve, Reject, Deny, or RequestChange. This procedure describes how to create a workflow approval in the AOT.

Depending on the needs of the business application, you can enable or disable workflow approval outcomes. The following table describes the four workflow approval outcome types.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Workflow outcome type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Complete</p></td>
<td><p>Completes the workflow approval and continues the workflow forward.</p>
> [!note]  
> <P>Each approval must have one outcome of type Complete.</P>
</td>
</tr>
<tr class="even">
<td><p>Return</p></td>
<td><p>Returns the approval to the originator for changes and resubmission back to workflow.</p></td>
</tr>
<tr class="odd">
<td><p>RequestChange</p></td>
<td><p>Sends the approval to a specific user for changes and resubmission back to workflow.</p></td>
</tr>
<tr class="even">
<td><p>Deny</p></td>
<td><p>Completes the approval as denies and continues the workflow forward.</p></td>
</tr>
</tbody>
</table>


### To create a workflow approval

1.  In the AOT, expand the **Workflow** node.

2.  Right-click the **Approvals** node, and then click **Add-Ins** \> **Approval wizard**. The **Workflow wizard** is displayed. This wizard will help you create a new workflow approval.

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
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>The name that will be used for the workflow approval.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Workflow document</strong></p></td>
    <td><p>The class that defines the workflow document for which you are creating an approval.</p>
    > [!note]  
    > <P>This setting must match the <strong>Document</strong> property setting used in the workflow type for the approval.</P>
    </td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document preview field group</strong></p></td>
    <td><p>The initial set of fields displayed in the unified work list. Select a field group from the root table specified in the <strong>Workflow document</strong> that you selected. The <strong>Workflow document</strong> value must be set before you can select a field group.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Document menu item</strong></p></td>
    <td><p>Choose the menu item that points to the main form that displays the document for which you are creating a workflow approval.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document web menu item</strong></p></td>
    <td><p>Choose the web menu item that points to the Enterprise Portal page that displays the document for which you are creating a workflow approval.</p></td>
    </tr>
    </tbody>
    </table>


5.  Specify which types of menu items you want to create. You can create menu items for the Microsoft Dynamics AX client, web menu items for Enterprise Portal, or items for both.

6.  Specify whether you want to enable the Deny outcome.

7.  Click **Next**. A list of all of the resources that will be created for the workflow approval is displayed.

8.  Click **Finish** to create the resources. The wizard will create classes, menu items, web menu items, the approval, and a project that contains all of the items.

9.  A dialog box will be displayed that indicates the status. Click **OK**. The project that contains the workflow type resources is displayed.

After a workflow approval is created, you can add the approval to the **Supported Elements** node of a workflow type. A workflow approval can be bound to more than one workflow type. For more information, see [How to: Add a Task, Automated Task, or Approval to a Workflow Type](how-to-add-a-task-automated-task-or-approval-to-a-workflow-type.md). To add code for the approval, see [Handling Workflow Events](handling-workflow-events.md).

## See also

[Creating a Workflow Type](creating-a-workflow-type.md)

[Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md)

[Workflow Approval Checklist](workflow-approval-checklist.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

