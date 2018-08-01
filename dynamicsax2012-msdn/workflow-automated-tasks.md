---
title: Workflow Automated Tasks
TOCTitle: Workflow Automated Tasks
ms:assetid: 968ccd54-dfcb-4eb1-9db6-f4a64e374186
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh457522(v=AX.60)
ms:contentKeyID: 37009277
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Automated Tasks [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Tasks can run automatically, or require user intervention. A workflow can contain both types of tasks. Automated tasks are workflow elements that are used to start X++ code in the application without requiring user intervention. When the workflow is started, an automated task could execute a customer credit check and send the results to the workflow owner. Based on the results of the credit check, the workflow owner can take action and continue the sales order workflow.

The business logic for an automated task must always run on the AOS and not the client. You can use an automated task to, for example, execute database transactions or updates.

Automated tasks do not have outcomes. Since there is no user interaction, the outcome of an automated task is one of the following: completed, not completed, or canceled. You can write custom business logic enclosed in event handlers to handle these outcomes.

  - [Workflow Automated Task Checklist](workflow-automated-task-checklist.md)

  - [How to: Create a Workflow Automated Task](how-to-create-a-workflow-automated-task.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

