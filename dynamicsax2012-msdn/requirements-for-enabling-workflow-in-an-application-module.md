---
title: Requirements for Enabling Workflow in an Application Module
TOCTitle: Requirements for Enabling Workflow in an Application Module
ms:assetid: 8cd4421d-8966-4dc2-ab52-4e52ef6f8c2c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc603594(v=AX.60)
ms:contentKeyID: 35246410
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Requirements for Enabling Workflow in an Application Module [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To enable a Microsoft Dynamics AX workflow for a new or existing application module, you must complete a series of required steps and then, depending on application requirements, complete additional steps. This topic describes the required steps to add workflow to your application.

## Required Steps

The following steps are necessary for every workflow:

1.  Create a state model. For more information about a recommended state model, see [Workflow Approval State Transitions](workflow-approval-state-transitions.md) and [How to: Enable a State Model for a Workflow Document](how-to-enable-a-state-model-for-a-workflow-document.md).

2.  Add a workflow display menu item. The workflow display menu item is used to access the workflow types for each module. For more information, see [How to: Create a New Module with Workflow](how-to-create-a-new-module-with-workflow.md).

3.  Create a workflow category. A workflow category filters workflow types to a single module. If adding a new module, extend the ModuleAxapta  **Base Enums** type. For more information, see [How to: Create a Workflow Category](how-to-create-a-workflow-category.md).

4.  Create a workflow document class to define the workflow document for the workflow. You will create a query, and if needed, add calculated fields to identify the derived fields available for conditions displayed in the workflow configuration tool. For more information, see [How to: Create a Workflow Document Class](how-to-create-a-workflow-document-class.md).

5.  Enable a form or list for workflow. You must set properties on a form or list to display the workflow button and controls. For more information, see [How to: Enable a Form or List for Workflow](how-to-enable-a-form-or-list-for-workflow.md).

6.  Enable documents to be submitted to the workflow. For more information, see [How to: Enable Workflow Submission](how-to-enable-workflow-submission.md).

7.  Create a workflow type. A workflow type defines information about which workflow document to use, tasks, automated tasks, approvals, line item workflows, workflow category, menu items, and event handlers. For more information, see [Creating a Workflow Type](creating-a-workflow-type.md).

8.  Activate the workflow. There are several ways to activate the workflow. For more information, see [Activating a Workflow](activating-a-workflow.md).

9.  Define and implement event handlers for the workflow, approvals, tasks, and automated tasks. For more information, see [Handling Workflow Events](handling-workflow-events.md).

10. Implement workflow providers for due date, participant, hierarchy, and queue assignment. For more information, see [Workflow Providers](workflow-providers.md).

11. Define and implement approvals, tasks, and automated tasks. For more information, see [Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md).

## Optional Steps

1.  Create custom workflow providers. For more information, see [How to: Create a Custom Workflow Provider](how-to-create-a-custom-workflow-provider.md).

2.  Create event handlers for tasks. For more information, see [How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md).

## See also

[Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

[Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

