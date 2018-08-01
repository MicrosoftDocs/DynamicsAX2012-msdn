---
title: 'How to: Create a Workflow Task'
TOCTitle: 'How to: Create a Workflow Task'
ms:assetid: 84465e44-5400-429e-917e-8ad88ecc3144
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc601939(v=AX.60)
ms:contentKeyID: 35246163
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Workflow Task [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX workflow task is a single unit of work that must be performed. A workflow may contain one or more tasks.

The following procedure describes how to create a new workflow task in the AOT.

### To create a workflow task

1.  In the **AOT**, expand the **Workflow** node.

2.  Right-click the **Tasks** node, and then click **Add-Ins** \> **Task wizard**. The **Workflow wizard** is displayed. This wizard will help you create a new workflow task.

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
    <td><p>The name that will be used for the workflow task.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Workflow document</strong></p></td>
    <td><p>The class that defines the workflow document for which you are creating a task.</p>
    
    > [!note]  
    > <P>This setting must match the <strong>Document</strong> property setting used in the workflow type for the task.</P>
    
    </td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document preview field group</strong></p></td>
    <td><p>The initial set of fields displayed in the unified work list. Select a field group from the root table specified in the <strong>Workflow document</strong> that you selected. The <strong>Workflow document</strong> value must be set before you can select a field group.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Document menu item</strong></p></td>
    <td><p>Choose the menu item that points to the main form that displays the document for which you are creating a workflow task.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document web menu item</strong></p></td>
    <td><p>Choose the web menu item that points to the Enterprise Portal page that displays the document for which you are creating a workflow task.</p></td>
    </tr>
    </tbody>
    </table>


5.  Specify which types of menu items you want to create. You can create menu items for the Microsoft Dynamics AX client, web menu items for Enterprise Portal, or items for both.

6.  Click **Next**.

7.  Define the task outcomes. For each outcome that you want to support, supply a **Name** for the outcome. The name cannot contain spaces. Specify the **Type** for the outcome. Choose one of the following types:
    
      - **Complete** - Completes the workflow task and continues the workflow forward.
    
      - **Return** - Returns the task to the originator for changes and then resubmission back to workflow.
    
      - **RequestChange** - Sends the task to a specified user for changes and then resubmission back to workflow.
    
      - **Deny** - Completes the task as denied and continues the workflow forward.
    
    Click **Add**.
    

    > [!NOTE]
    > <P>Each task must have one outcome of type <STRONG>Complete</STRONG>.</P>



8.  After you have finished defining the outcomes, click **Next**. A list of all of the resources that will be created for the workflow task is displayed.

9.  Click **Finish** to create the resources. The wizard will create classes, menu items, web menu items, the task, and a project that contains all of the items.

10. A dialog box will be displayed that indicates the status. Click **OK**. The project that contains the workflow type resources is displayed.

After a workflow task is created, you can add the workflow task to the **Supported Elements** node of a workflow type. For more information, see [How to: Add a Task, Automated Task, or Approval to a Workflow Type](how-to-add-a-task-automated-task-or-approval-to-a-workflow-type.md). To add code for the task, see [Handling Workflow Events](handling-workflow-events.md).

## See also

[Creating a Workflow Type](creating-a-workflow-type.md)

[Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md)

[Workflow Task Checklist](workflow-task-checklist.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

