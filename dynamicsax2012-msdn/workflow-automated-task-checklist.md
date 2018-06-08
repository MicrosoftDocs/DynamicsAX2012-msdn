---
title: Workflow Automated Task Checklist
TOCTitle: Workflow Automated Task Checklist
ms:assetid: 81fa4a49-7d8f-48f3-a1cc-b283542cacf0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862507(v=AX.60)
ms:contentKeyID: 35246149
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Automated Task Checklist 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following topic shows how you can create an automated task in a Microsoft Dynamics AX workflow. Before you create automated tasks, you must have a workflow type. For more information, see [Creating a Workflow Type](creating-a-workflow-type.md).

## Automated Task Checklist for a Workflow

1.  Create an automated task in the Application Object Tree (AOT). For more information, see [How to: Create a Workflow Automated Task](how-to-create-a-workflow-automated-task.md).

2.  Create automated task event handler classes for the **ExecutionEventHandler** and **CanceledEventHandler** property settings, and then bind the event handlers to the automated task. For more information, see [How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md).

3.  Set the **Document** property for the automated task to match the workflow type **Document** property setting. For more information, see [How to: Create a Workflow Document Class](how-to-create-a-workflow-document-class.md).

## See also

[How to: Create a Workflow Automated Task](how-to-create-a-workflow-automated-task.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

