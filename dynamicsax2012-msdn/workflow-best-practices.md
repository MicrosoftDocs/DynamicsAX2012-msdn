---
title: Workflow Best Practices
TOCTitle: Workflow
ms:assetid: 3dda947b-df91-4f3b-8b7d-eed13f024d1a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc597937(v=AX.60)
ms:contentKeyID: 35242939
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Best Practices 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Best practice checks for workflow focus on the properties of workflow categories, types, approvals, and tasks. The checks verify that the properties are correctly configured. For information about how to set the options for best practice checks, see [Best practice parameters](best-practice-parameters.md). This topic includes general principles to follow when you develop workflows and a table of the best practice checks and how to fix the errors.

## General Principles

When creating a query for a workflow document, consider the following:

  - Most document data is available to set up conditions for workflow. In addition, the query identifies workflow placeholders used in messages in the configuration user interface for instructions and notifications. Make sure to use placeholder fields that the end-user can understand and not fields that contain internal data not typically visible to users.

  - By default, all data fields with the Visible property in the table set to Yes are exposed for workflow conditions. To simplify the set up for workflow conditions, you can remove unnecessary data fields that will not be used for workflow conditions or placeholders in the configuration UI. To remove data fields, set the Dynamic property on the **Fields** node of the data source to No. Expand the **Fields** node, right-click a field, and then click **Delete**. If the query is not saved, the **Delete** command is not available.

  - Set the Relations property of the query to Yes if the query system should use the relations that are defined for tables and extended data types. When set to Yes, the query is automatically updated if a relation is changed.

  - Optionally, set the Join Mode property of the query to Outer Join. Records in one data source are joined even if there are no matching values in the joined field from the second data source. Only fields from Inner Join or Outer Join are visible in the configuration user interface as conditions and placeholders.

  - In the **Properties** sheet, set the Table property to the table that contains the data for the workflow document. The root table in the query should be the same as the workflow data source property of the form.

When creating task and approval elements in the Application Object Tree (AOT), be sure to use unique and declarative label names for the element. When adding an approval to a workflow configuration, the label Approval would not be unique enough for the user to determine which approval is to be added.

Use the [WorkflowWorkItemActionManager Class](https://msdn.microsoft.com/en-us/library/gg815458\(v=ax.60\)) to manage task or approval outcome action menu items for type Complete, Return, RequestChange, and Deny.

## Best Practice Checks

The following table lists the best practices error messages and how to fix the errors.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Message</p></th>
<th><p>Message type</p></th>
<th><p>How to fix the error or warning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuration key not defined</p></td>
<td><p>Error</p></td>
<td><p>The workflow type or a workflow element ConfigurationKey property setting is invalid or not defined. Set the ConfigurationKey property to a valid setting. This property is optional.</p></td>
</tr>
<tr class="even">
<td><p>Workflow document not defined</p></td>
<td><p>Error</p></td>
<td><p>The workflow type, task, automated task, or approval Document property setting is invalid or not defined. Set the Document property to a valid setting. For more information, see <a href="how-to-create-a-workflow-document-class.md">How to: Create a Workflow Document Class</a>. This property is required.</p></td>
</tr>
<tr class="odd">
<td><p>Workflow document does not reference a valid class deriving from the <a href="https://msdn.microsoft.com/en-us/library/gg798542(v=ax.60)">WorkflowDocument Class</a></p></td>
<td><p>Error</p></td>
<td><p>The workflow type, task, automated task, or approval Document property setting must reference a class that extends the <a href="https://msdn.microsoft.com/en-us/library/gg798542(v=ax.60)">WorkflowDocument Class</a> and overrides the <a href="https://msdn.microsoft.com/en-us/library/gg798541(v=ax.60)">WorkflowDocument.getQueryName Method</a>. The class was probably deleted, renamed, or no longer extends the <a href="https://msdn.microsoft.com/en-us/library/gg798542(v=ax.60)">WorkflowDocument Class</a>. For more information, see <a href="how-to-create-a-workflow-document-class.md">How to: Create a Workflow Document Class</a>.</p></td>
</tr>
<tr class="even">
<td><p>The action menu item is not defined. The action menu item or the action Web menu item must be defined.</p></td>
<td><p>Error</p></td>
<td><p>The task or approval ResubmitMenuItem or DelegateMenuItem property setting is invalid or not defined. Set the menu item to a valid setting. For more information, see <a href="how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md">How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome</a>. This property is optional.</p></td>
</tr>
<tr class="odd">
<td><p>Reference to action menu item is invalid</p></td>
<td><p>Error</p></td>
<td><p>The workflow type, task, or approval menu item property setting is invalid or no longer exists. The action menu item was probably deleted or renamed. For more information, see <a href="creating-a-workflow-type.md">Creating a Workflow Type</a>.</p></td>
</tr>
<tr class="even">
<td><p>Reference to web action menu item is invalid</p></td>
<td><p>Error</p></td>
<td><p>The workflow type, task, or approval web menu item property setting is invalid or no longer exists. The web action menu item was probably deleted or renamed. For more information, see <a href="creating-a-workflow-type.md">Creating a Workflow Type</a>.</p></td>
</tr>
<tr class="odd">
<td><p>The document menu item is not defined. The document menu item or the document Web menu item must be defined.</p></td>
<td><p>Error</p></td>
<td><p>The task or approval display DocumentMenuItem property setting is invalid or not defined. Set the menu item to a valid setting. For more information, see <a href="how-to-associate-a-display-menu-item-with-a-workflow-task-or-approval.md">How to: Associate a Display Menu item with a Workflow Task or Approval</a>. This property is required.</p></td>
</tr>
<tr class="even">
<td><p>Reference to display menu item is invalid</p></td>
<td><p>Error</p></td>
<td><p>The task or approval display DocumentMenuItem property setting is invalid or no longer exists. The display menu item was probably deleted or renamed. For more information, see <a href="how-to-create-a-workflow-task.md">How to: Create a Workflow Task</a> and <a href="how-to-create-a-workflow-approval.md">How to: Create a Workflow Approval</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Reference to Web URL menu item is invalid</p></td>
<td><p>Error</p></td>
<td><p>The task or approval display DocumentWebMenuItem property setting is invalid or no longer exists. The display menu item was probably deleted or renamed. For more information, see <a href="how-to-create-a-workflow-task.md">How to: Create a Workflow Task</a> and <a href="how-to-create-a-workflow-approval.md">How to: Create a Workflow Approval</a>.</p></td>
</tr>
<tr class="even">
<td><p>Event handler should be defined</p></td>
<td><p>Warning</p></td>
<td><p>The task or approval EventHandler property is invalid or not defined. Set the EventHandler property to the event handler for that workflow element. For more information, see <a href="handling-workflow-events.md">Handling Workflow Events</a>. This property setting is optional. However, when an event handler is not defined, no application logic will run when this event is triggered.</p></td>
</tr>
<tr class="odd">
<td><p>Event handler not defined</p></td>
<td><p>Error</p></td>
<td><p>The task or approval outcome EventHandler property is not valid or defined. Set the EventHandler property to the event handler for that workflow element. For more information, see <a href="handling-workflow-events.md">Handling Workflow Events</a>. This property is required for all outcomes that are enabled.</p></td>
</tr>
<tr class="even">
<td><p>Event handler does not reference a valid class implementing the '%1' interface</p></td>
<td><p>Error</p></td>
<td><p>All workflow type event handlers must implement the appropriate workflow interface. For example, the <a href="https://msdn.microsoft.com/en-us/library/gg829764(v=ax.60)">WorkflowCompletedEventHandler Interface</a> must be implemented by the class that is referenced by the workflow type CompletedEventHandler property setting. For more information, see <a href="handling-workflow-events.md">Handling Workflow Events</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Module not defined</p></td>
<td><p>Warning</p></td>
<td><p>The workflow category Module property setting refers to a module that is invalid or no longer exists. The module was probably deleted or renamed. For more information, see <a href="https://msdn.microsoft.com/en-us/library/gg882682(v=ax.60)">ModuleAxapta Enumeration</a>. This property is required.</p></td>
</tr>
<tr class="even">
<td><p>Category not defined</p></td>
<td><p>Error</p></td>
<td><p>The workflow type Category property setting is not defined. Set the workflow type Category property setting to a valid category. This property is required.</p></td>
</tr>
<tr class="odd">
<td><p>Invalid reference to workflow category</p></td>
<td><p>Error</p></td>
<td><p>The workflow type Category property setting is invalid or no longer exists. The category was probably deleted or renamed. For more information, see <a href="how-to-create-a-workflow-category.md">How to: Create a Workflow Category</a>.</p></td>
</tr>
<tr class="even">
<td><p>Required element '%1' does not reference same document as the workflow template</p></td>
<td><p>Error</p></td>
<td><p>The Document property setting of the specified task, automated task, or approval workflow element in the workflow type <strong>Supported Elements</strong> node does not match the Document property setting of the workflow type. Set the specified workflow element Document property setting to match the workflow type Document property setting. For more information, see <a href="how-to-create-a-workflow-task.md">How to: Create a Workflow Task</a> and <a href="how-to-create-a-workflow-approval.md">How to: Create a Workflow Approval</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Approve outcome must exist and be enabled</p></td>
<td><p>Error</p></td>
<td><p>The <strong>Approve</strong> outcome in the approval <strong>Outcomes</strong> node has the Enabled property setting set to No. Each approval must have at least one enabled outcome of type Complete and an action menu item for the approval work item button to display in the user interface. For more information, see <a href="how-to-create-a-workflow-approval.md">How to: Create a Workflow Approval</a>.</p></td>
</tr>
<tr class="even">
<td><p>The element outcome '%1' action menu item property is not defined. The action menu item or the action Web menu item must be defined.</p></td>
<td><p>Error</p></td>
<td><p>The specified task or approval outcome action menu item is invalid or not defined. Set the action menu item to a valid setting. For more information, see <a href="how-to-associate-an-action-menu-item-with-a-workflow-task-or-approval-outcome.md">How to: Associate an Action Menu Item with a Workflow Task or Approval Outcome</a>. This property is optional.</p></td>
</tr>
<tr class="odd">
<td><p>Element outcome '%1' ActionWebMenuItem property does not reference a valid web action menu item</p></td>
<td><p>Error</p></td>
<td><p>The specified task or approval outcome action web menu item is invalid or no longer exists. The specified action web menu item was probably deleted or renamed. For more information, see <a href="how-to-create-a-workflow-task.md">How to: Create a Workflow Task</a> and <a href="how-to-create-a-workflow-approval.md">How to: Create a Workflow Approval</a>.</p></td>
</tr>
<tr class="even">
<td><p>Element outcome '%1' ActionMenuItem property does not reference a valid action menu item</p></td>
<td><p>Error</p></td>
<td><p>The specified task or approval outcome action menu item is invalid or no longer exists. The specified action menu item was probably deleted or renamed. For more information, see <a href="how-to-create-a-workflow-task.md">How to: Create a Workflow Task</a> and <a href="how-to-create-a-workflow-approval.md">How to: Create a Workflow Approval</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Element outcome '%1' EventHandler property should be defined</p></td>
<td><p>Warning</p></td>
<td><p>The specified task or approval event handler is invalid or not defined. Set the event handler to a valid setting. For more information, see <a href="handling-workflow-events.md">Handling Workflow Events</a>. This property is optional. However, when an event handler is not defined, no application logic will run when this event is triggered.</p></td>
</tr>
<tr class="even">
<td><p>Element outcome '%1' EventHandler property does not reference a valid class implementing the '%2' interface</p></td>
<td><p>Error</p></td>
<td><p>The specified task and approval outcome event handler property setting must reference a class that implements the associate event handler interface. An approval, for example, has an <strong>Approve</strong> outcome of type Complete and the EventHandler property setting must reference a class that implements the <a href="https://msdn.microsoft.com/en-us/library/gg831404(v=ax.60)">WorkflowElementCompletedEventHandler Interface</a>. For more information, see <a href="handling-workflow-events.md">Handling Workflow Events</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Task outcomes must contain one enabled outcome of type Complete</p></td>
<td><p>Error</p></td>
<td><p>There are no enabled outcomes in the task <strong>Outcomes</strong> node of type Complete. Each task must have at least one enabled outcome of type Complete and an action menu item for the task work item button to display in the user interface. For more information, see <a href="how-to-create-a-workflow-task.md">How to: Create a Workflow Task</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Workflow Security](workflow-security.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

