---
title: 'How to: Create a Workflow Automated Task'
TOCTitle: 'How to: Create a Workflow Automated Task'
ms:assetid: df1b21fc-49f3-4016-ac90-6d7cd25bf09e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg864388(v=AX.60)
ms:contentKeyID: 35252088
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Workflow Automated Task 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create Microsoft Dynamics AX workflow automated tasks as a step within a work process. A workflow may contain one or more automated tasks. This procedure describes how to create a new automated task for a workflow in the AOT.

### To create an automated task

1.  In the AOT, expand the **Workflow** node.

2.  Right-click the **Automated Tasks** node and then select **New Automated Task**. A new automated task displays under the **Automated Tasks** node.

3.  Right-click the new automated task and then click **Properties**.

4.  In the **Properties** sheet, set the following properties as required.
    
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
    <td><p>The name that is used to reference the automated task.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>The label used for the automated task in the user interface.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Help Text</strong></p></td>
    <td><p>The description of the automated task shown in the workflow configuration user interface.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ConfigurationKey</strong></p></td>
    <td><p>The configuration key assigned to the automated task.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document</strong></p></td>
    <td><p>The workflow document that the automated task is associated with.</p>
    <div class="mtps-table">
    <div class="mtps-row">
    <img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
    </div>
    <div class="mtps-row">
    This setting must match the <strong>Document</strong> property setting used in the workflow type for the workflow.
    </div>
    </div></td>
    </tr>
    <tr class="even">
    <td><p><strong>ExecutionEventHandler</strong></p></td>
    <td><p>The workflow event handler that executes when the automated task is called in the workflow. This property is mandatory.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CanceledEventHandler</strong></p></td>
    <td><p>The workflow event handler that executes when the workflow canceled event is raised. This property is optional.</p></td>
    </tr>
    </tbody>
    </table>


After an automated task is created, you can add the automated task to a workflow type in the **Supported Elements** node. For more information, see [Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md).

## See also

[Creating a Workflow Type](creating-a-workflow-type.md)

[Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md)

[Workflow Automated Task Checklist](workflow-automated-task-checklist.md)

[How to: Create a Workflow Task or Approval Event Handler](how-to-create-a-workflow-task-or-approval-event-handler.md)

[Walkthrough: Adding an Automated Task to a Workflow](walkthrough-adding-an-automated-task-to-a-workflow.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

