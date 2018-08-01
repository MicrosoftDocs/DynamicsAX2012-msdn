---
title: Workflow Approvals
TOCTitle: Workflow Approvals
ms:assetid: b993f038-620f-4ef2-8f7a-2c8cf51ca92b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh457524(v=AX.60)
ms:contentKeyID: 37009279
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Approvals [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Approvals are specialized workflow elements designed to support approval scenarios. Approvals have a set of fixed outcomes that the workflow supports. These outcomes are as follows:

  - **Approve** - Outcome type **Complete**.

  - **Reject** - Outcome type **Return** to the originator of the workflow.

  - **RequestChange** - Outcome type **ChangeRequested** to a specific person in the workflow process.

  - **Deny** - Outcome type **Deny**.
    

    > [!NOTE]
    > <P>The fixed outcomes listed earlier cannot be deleted in the AOT. However, you can set the workflow outcome Enabled property to No to disable the workflow outcome in the application.</P>



Each approval outcome can be associated with a specific action web menu item, action menu item, and event handler. The action web menu item displays the action button name and dialog box when this action is selected from the Enterprise Portal work list or Enterprise Portal workflow controls. The action menu item displays the action button name and dialog box when this action is selected from the unified work list or the client workflow controls.

Each approval must have one outcome of type **Complete**.

  - [Workflow Approval Checklist](workflow-approval-checklist.md)

  - [How to: Create a Workflow Approval](how-to-create-a-workflow-approval.md)

  - [Workflow Approval State Transitions](workflow-approval-state-transitions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

