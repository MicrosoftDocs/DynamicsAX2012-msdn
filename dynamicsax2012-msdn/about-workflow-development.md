---
title: About Workflow Development
TOCTitle: About Workflow Development
ms:assetid: dab84362-fe13-4873-ab9d-d4b6dcbd13ba
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967429(v=AX.60)
ms:contentKeyID: 35252071
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# About Workflow Development [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Workflow is defined as the movement of documents or tasks through a work process. In Microsoft Dynamics AX, the focus of workflow is on approval and task-oriented workflows. The developer role in Microsoft Dynamics AX is primarily to add workflow to existing business documents or create new documents that support workflow. This topic describes what the workflow life cycle is and the developer role for a workflow in Microsoft Dynamics AX.

Workflow can be described as structured or unstructured. In Microsoft Dynamics AX, workflow is structured and based on user interaction and system automation of business data. For example, when a purchase requisition (business data) is created it, workflow can be used to verify and approve the data.

## Workflow Lifecycle

All workflows follow a basic life cycle as shown in the following illustration.

![Workflow Lifecycle](images/Cc967429.WorkflowOverview(en-us,AX.60).gif "Workflow Lifecycle")

You design the workflow based on customer requirements. The company administrator configures the workflow, and users run the workflow. This section describes the some of the main development concepts used in the design section of the workflow life cycle in Microsoft Dynamics AX.

### ![Cc967429.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967429.collapse_all(en-us,AX.60).gif")Workflow types

The workflow type is a building block that can be used to create customized workflows that enforce business policies. The workflow type is defined in the Application Object Tree (AOT) at design time. The metadata from the workflow type is used by the customer to create a workflow configuration. For more information, see [Creating a Workflow Type](creating-a-workflow-type.md).

### ![Cc967429.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967429.collapse_all(en-us,AX.60).gif")Workflow configurations

Workflow configurations are created by application administrators that use the Microsoft Dynamics AX workflow editor. The administrator configures the workflow, workflow elements, and approval steps that control the flow of the business document though the workflow process. For example, the configuration data for a workflow task describes what type of business calendar to use to determine the due date of the task.

### ![Cc967429.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967429.collapse_all(en-us,AX.60).gif")Workflow instances

A workflow instance is created by the workflow runtime when a workflow is activated.

### ![Cc967429.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967429.collapse_all(en-us,AX.60).gif")Workflow elements

The elements of a workflow are created by you in the AOT and configured by application administrators. The workflow structure consists of sequences of workflow elements. An element can be a task, automated task, approval, or a sub-workflow. For more information, see [Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md).

Approvals are specialized workflow elements that allow for sequencing of multiple steps, which use a fixed set of outcomes. Tasks are generic workflow elements that represent a single unit of work which use custom outcomes defined by the developer. Automated tasks are workflow elements used to invoke X++ code within the application without requiring human intervention.

### ![Cc967429.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967429.collapse_all(en-us,AX.60).gif")Work items

Work items are the units of work created by the workflow at runtime. They are the main interface between the end user who participates in a workflow and the workflow runtime. All work items for users who are logged on are surfaced in the **Unified Work List** and are used to inform a user about work assignments.

## Developer Role

You must create the workflow artifacts, dependent workflow artifacts, and business logic to support the workflow. The following sections describe most of the developer artifacts used in a Microsoft Dynamics AX workflow.

### ![Cc967429.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967429.collapse_all(en-us,AX.60).gif")Workflow Artifacts

  - Workflow type
    
      - Define the workflow document. For more information, see [How to: Create a Workflow Document Class](how-to-create-a-workflow-document-class.md).
    
      - Define event handlers for workflow **Started**, **Completed**, **ConfigDataChanged**, and **Canceled**. For more information, see [Handling Workflow Events](handling-workflow-events.md).
    
      - Define menu items used for the workflow type like **Submit**. For more information, see [Creating a Workflow Type](creating-a-workflow-type.md).
    
      - Define the workflow category.
    
      - Define required approvals, tasks, and automated tasks. For more information, see [How to: Add a Task, Automated Task, or Approval to a Workflow Type](how-to-add-a-task-automated-task-or-approval-to-a-workflow-type.md).
    
      - Enable and disable activation conditions.

  - Workflow category
    
      - Define the module that the workflow type is enabled in. For more information, see [How to: Create a Workflow Category](how-to-create-a-workflow-category.md).

  - Approval
    
      - Define the approval workflow document.
    
      - Define approval event handlers for **Started** and **Canceled**.
    
      - Define approval menu items such as **Document**, **Resubmit**, and **Delegate**.
    
      - Enable or disable fixed approval outcomes.
    
      - Define approval outcome menu items for **Action** and **ActionWeb**.
    
      - Define approval outcome event handler.
    
      - Define the **DocumentPreviewFieldGroup**.

  - Task
    
      - Define the task workflow document.
    
      - Define task event handlers for **Started** and **Canceled**.
    
      - Define task menu items for **Document**, **DocumentWeb**, **Resubmit**, **ResubmitWeb**, **Delegate**, and **DelegateWeb**.
    
      - Enable or disable task outcomes.
    
      - Define task outcome menu items for **Action** and **ActionWeb**.
    
      - Define task outcome event handler.
    
      - Define the **DocumentPreviewFieldGroup**.

  - Automated Task
    
      - Define the automated task workflow document.
    
      - Define automated task event handlers for **Execution** and **Canceled**.

### ![Cc967429.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967429.collapse_all(en-us,AX.60).gif")Dependent Workflow Artifacts

The following workflow artifacts are dependent upon the type of workflow defined in the AOT.

  - Workflow Document class - identifies the document query and any calculated fields. For more information, see [How to: Create a Workflow Document Class](how-to-create-a-workflow-document-class.md).
    
      - Document query - defined in the AOT to expose data that is used for conditions in the configuration user interface.

  - SubmitToWorkflow class - displays the **Submit to Workflow** dialog box in the user interface, receives user comments, activates the workflow, and can update workflow state. For more information, see [How to: Create a SubmitToWorkflow Class](how-to-create-a-submittoworkflow-class.md) and [Activating a Workflow](activating-a-workflow.md).

  - State model - tracks the state of the document in the workflow process, for example, Submitted, ChangeRequested, or Approved. For more information, see [How to: Enable a State Model for a Workflow Document](how-to-enable-a-state-model-for-a-workflow-document.md).

  - Event handlers for the workflow itself on the workflow type, approval, approval outcomes, automated task, task, and task outcomes.

  - Action and display menu items as well as classes which determine the action taken when a menu item is selected in the user interface.

  - Custom workflow providers. For more information, see [How to: Create a Custom Workflow Provider](how-to-create-a-custom-workflow-provider.md).

  - canSubmitToWorkflow method - required on each table enabled for workflow. For more information, see [How to: Enable a Form or List for Workflow](how-to-enable-a-form-or-list-for-workflow.md).

## See also

[Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md)

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

[Workflow Type Checklist](workflow-type-checklist.md)

[Workflow Approval Checklist](workflow-approval-checklist.md)

[Workflow Task Checklist](workflow-task-checklist.md)

[Workflow Automated Task Checklist](workflow-automated-task-checklist.md)

[Workflow Events Overview](workflow-events-overview.md)

[Workflow Providers Overview](workflow-providers-overview.md)

[Workflow Security](workflow-security.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

