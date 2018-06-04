---
title: Troubleshooting Workflow in Microsoft Dynamics AX
TOCTitle: Troubleshooting Workflow in Microsoft Dynamics AX
ms:assetid: a7b3b4b3-e712-4185-acef-432e45a83934
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc616520(v=AX.60)
ms:contentKeyID: 35248486
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Troubleshooting Workflow in Microsoft Dynamics AX 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes common problems that can occur when you develop and test a workflow in Microsoft Dynamics AX.

## General

The first step in troubleshooting a workflow problem is to see whether there are any Microsoft Dynamics AX best practice recommendations. To check best practices, right-click a workflow type in the AOT, point to **Add-Ins**, and then click **Check best practices**. Implement the recommendations and then repeat the best practices check for each related workflow node. For more information, see [Workflow Best Practices](workflow-best-practices.md).

To troubleshoot workflow X++ code, you must first set up debugging. For more information, see [How to: Debug X++ Code in Workflow](how-to-debug-x-code-in-workflow.md).

## Troubleshooting Workflow at Design Time

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")My new module is not available in the workflow category Module property setting

To view a new module name in the workflow category **Module** property drop-down list, it must be added to the **ModuleAxapta** enum. In the Application Object Tree (AOT), expand the **Data Dictionary** node, expand the **Base Enums** node, right-click **ModuleAxapta**, and then click **New Element**.

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")The Document class for my workflow type, task, or approval is not available in the Document property drop-down list

Only classes that extend the [WorkflowDocument Class](https://msdn.microsoft.com/en-us/library/gg798542\(v=ax.60\)) are displayed in the Document property drop-down list.

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")The event handler for my workflow task, automated task, or approval is not available in the property drop-down list

Only classes that implement the event handler interface are visible in the property drop-down list for event handlers. For more information, see [How to: Create a Workflow Task or Approval Event Handler](how-to-create-a-workflow-task-or-approval-event-handler.md).

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")My changes are not visible in the client.

Changes in metadata are not visible in the client immediately. To view changes in metadata in the client, close and restart the client.

## Troubleshooting Workflow at Configuration Time

You can use the **Tutorial\_WorkflowProcessor** form in the AOT **Forms** node to simulate batch processing for a workflow. Open the form and then click **Start** to run the processor. The results of the batch processing simulation can be viewed in the **Workflow History** form. In Microsoft Dynamics AX, click **Home** \> **Area page** \> **Inquiries** \> **Workflow** \> **Workflow history**.

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")My workflow type does not appear in the configuration user interface

Any one or combination of the following items can prevent the display of a workflow type in the configuration user interface. Running the best practice checks for a workflow type node is the easiest method to identify problems. For more information, see [Best Practices Checks](best-practices-checks.md).

  - Task and approvals must have an outcome of type Complete. For more information, see [How to: Create a Workflow Task](how-to-create-a-workflow-task.md) and [How to: Create a Workflow Approval](how-to-create-a-workflow-approval.md).

  - The class defined in the workflow type Document property setting must override the [WorkflowDocument.getQueryName Method](https://msdn.microsoft.com/en-us/library/gg798541\(v=ax.60\)). For more information, see [How to: Create a Workflow Document Class](how-to-create-a-workflow-document-class.md).

  - The Category property setting is required on all workflow types. For more information, see [How to: Create a Workflow Category](how-to-create-a-workflow-category.md).

  - The Category property setting on the workflow type is incorrect for the module running the configuration user interface. For more information, see [ModuleAxapta Enumeration](https://msdn.microsoft.com/en-us/library/gg882682\(v=ax.60\)).

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")My task or approval does not display in the configuration user interface

A task or approval will not display in the configuration user interface unless the Document property setting is identical to the workflow type Document property setting.

## Troubleshooting Workflow at Runtime

Problems can occur with a workflow at runtime that cannot be seen at design time or configuration time. Therefore, we recommend that you test the workflow and the configuration in a test environment before you implement the solution. You can use the **Tutorial\_WorkflowProcessor** form to simulate the batch process for testing.

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")The Submit button is not available on the workflow document form

  - Close and restart the client. Changes made to metadata are not immediately reflected in the user interface.

  - You must override the canSubmitToWorkflow method and it must return true to display the **Submit** button. For more information, see [How to: Enable a Form or List for Workflow](how-to-enable-a-form-or-list-for-workflow.md).
    

    > [!NOTE]
    > <P>If there are no records in the data source and the canSubmitToWorkflow method returns true, an exception is thrown. Therefore, you should programatically check for a record when you evaluate the state of the workflow.</P>



  - An action menu item is required to enable display of the **Submit** button for the SubmitToWorkflow class that you must create for each workflow type. For more information, see [How to: Create a SubmitToWorkflow Class](how-to-create-a-submittoworkflow-class.md).

  - All display and action menu items must point to a class that contains a main method.

  - The form must be enabled for workflow. For more information, see [How to: Enable a Form or List for Workflow](how-to-enable-a-form-or-list-for-workflow.md).

  - The form must have data and a line of data must be selected for the workflow.

  - There are no default configurations for the workflow.

  - There is a default configuration for the workflow, but it is not selected as **Active**. At least one configuration must be selected as active.

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")The workflow stops after the Submit button is clicked

  - If you use the WorkflowWorkCalendarDueDate provider, work items must have valid **Working Times** available in the system calendar to complete the work item. To set working times, go to **Organization administration** \> **Common** \> **Calendars** \> **Calendars**.

  - Is the workflow execution account set up for workflow? Open **System administration** \> **Setup** \> **System** \> **System service accounts**. On the **System service accounts** form, set an **Alias** and **Network domain** for the **Workflow execution account**.

  - Verify that the batch job is running or if the workflow batch job is in the batch job queue.

  - Check the Windows event log on the AOS.

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")My task and approval outcome is not available on the workflow document form

  - Set the Enabled property setting for a task or approval outcome to Yes.

  - Each task or approval outcome must have the ActionMenuItem property defined.

### ![Cc616520.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616520.collapse_all(en-us,AX.60).gif")There are unwanted spaces in my approval actions list

Set the Enabled property setting for task or approval outcomes that are not used in a workflow to No.

## See also

[Workflow Best Practices](workflow-best-practices.md)

[Workflow Security](workflow-security.md)

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

[Workflow Events Overview](workflow-events-overview.md)

[Workflow Providers Overview](workflow-providers-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

