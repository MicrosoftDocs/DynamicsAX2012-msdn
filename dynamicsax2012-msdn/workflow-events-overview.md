---
title: Workflow Events Overview
TOCTitle: Workflow Events Overview
ms:assetid: 468268f3-05d0-4f23-a351-79e5068f2b5f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc588240(v=AX.60)
ms:contentKeyID: 35243003
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Events Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Workflow event handlers in Microsoft Dynamics AX enable you to run application-specific business logic at key points during workflow execution. Workflow events are implemented at the workflow level and the workflow element level. You can insert business logic at the following events in the workflow.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Workflow level</p></th>
<th><p>Event</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Workflow type</p></td>
<td><p>StartedEventHandler</p>
<p>CompletedEventHandler</p>
<p>CanceledEventHandler</p>
<p>ConfigDataChangeEventHandler</p></td>
</tr>
<tr class="even">
<td><p>Approval</p></td>
<td><p>StartedEventHandler</p>
<p>CanceledEventHandler</p>
<p>WorkItemsCreatedEventHandler</p></td>
</tr>
<tr class="odd">
<td><p>Approval outcome</p></td>
<td><p>EventHandler</p></td>
</tr>
<tr class="even">
<td><p>Task</p></td>
<td><p>StartedEventHandler</p>
<p>CanceledEventHandler</p>
<p>WorkItemsCreatedEventHandler</p></td>
</tr>
<tr class="odd">
<td><p>Task outcome</p></td>
<td><p>EventHandler</p></td>
</tr>
<tr class="even">
<td><p>Automated Task</p></td>
<td><p>ExecutionEventHandler</p>
<p>CanceledEventHandler</p></td>
</tr>
</tbody>
</table>


You can subscribe to workflow or workflow element level events by creating an X++ class that implements the appropriate workflow event handler interface. Then you can set the event handler property on the workflow type, approval, outcome, task, and automated task to point to that implementation.

The following sections explain the different types of event handlers and guidelines for using them throughout your workflow.

## Workflow Level Event Handlers

At the workflow level, event handlers are provided for the workflow started, completed, canceled, and configuration data change events. For example, an event handler could transition a workflow that is canceled by the user from PendingApproval to NotSubmitted. Typically, the event handler stubs for workflow-level events are created by the **Workflow wizard** when you create a new workflow type. The following table lists the workflow-level events.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Event</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkflowStartedEventHandler</p></td>
<td><p>This event raises when the workflow instance starts.</p></td>
</tr>
<tr class="even">
<td><p>WorkflowCompletedEventHandler</p></td>
<td><p>This event raises when the workflow instance ends after it is completed.</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowCanceledEventHandler</p></td>
<td><p>This event raises when the workflow instance ends after it is canceled. Use this event handler to perform any cleanup operations needed.</p></td>
</tr>
<tr class="even">
<td><p>WorkflowConfigDataChangeEventHandler</p></td>
<td><p>This event raises when the workflow configuration data changes. Use this event handler to identify when a configuration has changed. For example, if you create an association between the application data and a workflow configuration, this event handler would raise if the configuration was deleted or updated.</p></td>
</tr>
</tbody>
</table>


We recommend that you implement multiple event handler interfaces in a single class to reduce the number of classes shown in the Application Object Tree (AOT). For example, the following workflow event handler code example implements the Started, Canceled, and Completed event handlers in one class.

```X++
    public class WorkflowEventHandler implements
        WorkflowStartedEventHandler,
        WorkflowCanceledEventHandler,
        WorkflowCompletedEventHandler
    {
    }
    public void started(WorkflowEventArgs _workflowEventArgs)
    {
        // ToDo Insert code for the workflow started eventhandler;
    }
     
    public void canceled(WorkflowEventArgs _workflowEventArgs)
    {
        // ToDo Insert code for the workflow canceled eventhandler;
    }
     
    public void completed(WorkflowEventArgs _workflowEventArgs)
    {
        // ToDo Insert code for the workflow completed eventhandler;
    }
```

## Element Level Event Handlers

Task, automated task, and approval event handlers are implemented at the workflow element level. Typically, the event handler stubs for element-level events are created by the **Workflow wizard** when you create a new workflow approval or workflow task. Event handlers are provided for the started, execution, canceled, approved, denied, rejected, request change, completed, and returned events. The following table lists the element-level events.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Event</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkflowElementStartedEventHandler</p></td>
<td><p>This event raises when the task or approval starts.</p>
<p>For approvals, you can use this event to transition the workflow document state from Submitted to PendingApproval.</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementCanceledEventHandler</p></td>
<td><p>This event raises when the task or approval is canceled.</p>
<p>For approvals, you can use this event to transition the workflow document state from the current state to NotSubmitted.</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementCompletedEventHandler</p></td>
<td><p>This event raises when the task or approval is completed.</p>
<p>For approvals, you can use this event to transition the workflow document state from PendingApproval to Approved.</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementReturnedEventHandler</p></td>
<td><p>This event raises when the task or approval is returned to the originator.</p>
<p>For approvals, you can use this event to transition the workflow document state from the current state to RequestChange.</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowElementDeniedEventHandler</p></td>
<td><p>This outcome event type is raised when a task or approval is denied. You can use this kind of outcome when you want a workflow to continue even though the approval step of the workflow is denied.</p>
<p>For approvals, you can use this event to transition the workflow document state from PendingApproval to Rejected.</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElemChangeRequestedEventHandler</p></td>
<td><p>This event is raised when an approver requests a change to the task or approval. The approval owner requesting a change can assign the workflow to any user without canceling the workflow instance.</p>
<p>For approvals, you can use this event to transition the workflow document state from PendingApproval to ChangeRequested.</p></td>
</tr>
</tbody>
</table>


For tasks, you might only implement some of these event handlers. For example, the started event handler can be used to transition the workflow document state from NotSubmitted to Submitted.

For approvals, you should implement all of the event handlers and use them to transition the state of the business document. For more information, see [Workflow Approval State Transitions](workflow-approval-state-transitions.md).


> [!NOTE]
> <P>The Return and ChangeRequested events share the same state in the recommended workflow state model. You can implement these two different events to distinguish between a workflow that is returned and a workflow that only needs a change. However, in both events, the behavior is the same in that a work item is created, and after the work item is complete, the document state is returned to Started.</P>



We recommend that you implement multiple event handler interfaces in a single class to reduce the number of classes shown in the AOT. For example, the following approval event handler code example implements the Started, Completed, ChangeRequested, Returned, and Canceled event handlers in one class.


> [!NOTE]
> <P>Create a single class for each task outcome that has more than one outcome of the same type. For example, a task may have an outcome of type Complete for both SendE-Mail or SendLetter.</P>



```X++
    Public class ApprovalEventHandler implements
        WorkflowElementStartedEventHandler,
        WorkflowElementCompletedEventhandler,
        WorkflowElementChangeRequestedEventHandler,
        WorkflowElementReturnedEventHandler,
        WorkflowElementCanceledEventHandler
    {
    }
    public void started(WorkflowElementEventArgs _workflowElementEventArgs)
    {
        // ToDo Insert code for the approval started eventhandler;
    }
     
    public void completed(WorkflowElementEventArgs _workflowElementEventArgs)
    {
        // ToDo Insert code for the approval completed eventhandler;
    }
     
    public void changeRequested(WorkflowElementEventArgs _workflowElementEventArgs)
    {
        // ToDo Insert code for the approval changeRequested eventhandler;
    }
    public void returned(WorkflowElementEventArgs _workflowElementEventArgs)
    {
        // ToDo Insert code for the approval returned eventhandler;
    }
     
    public void canceled(WorkflowElementEventArgs _workflowElementEventArgs)
    {
        // ToDo Insert code for the approval canceled eventhandler;
    }
```

## Implementing Event Handlers

When the workflow infrastructure calls the event handlers at the workflow and the workflow element level, it passes WorkflowEventArgs or WorkflowElementEventArgs that contains the workflow context. The following example shows the workflow context for the WorkflowElementEventArgs.

```X++
class WorkflowElementEventArgs
    {
        WorkflowContext workflowContext;
    }
    public WorkflowContext parmWorkflowContext(
        WorkflowContext _workflowContext = workflowContext)
    {
        workflowContext = _workflowContext;
        return workflowContext;
    }
```

The workflow context consists of the following:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CompanyId</p></td>
<td><p>The company ID that the workflow belongs to.</p></td>
</tr>
<tr class="even">
<td><p>TableId</p></td>
<td><p>The table ID identifies which workflow document is used for the workflow.</p></td>
</tr>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>The record ID of the workflow document associated with the workflow.</p></td>
</tr>
<tr class="even">
<td><p>SubWorkflowId</p></td>
<td><p>The identifier for the subworkflow.</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowCorrelationId</p></td>
<td><p>A unique correlation ID of the running workflow instance. This parameter is used by the workflow infrastructure to ensure uniqueness of the workflow.</p></td>
</tr>
</tbody>
</table>


The following code example returns the record ID workflow context for a workflow element.

```X++
void started(WorkflowElementEventArgs _workflowElementEventArgs)
    {
        WorkflowContext workflowContext;
        ;
        workflowContext = _workflowElementEventArgs.parmWorkflowContext();
        // ToDo <Insert code for the event> (workflowContext.parmRecId());
    }
```

## See also

[Workflow Approval State Transitions](workflow-approval-state-transitions.md)

[How to: Create a Workflow Event Handler](how-to-create-a-workflow-event-handler.md)

[How to: Create a Workflow Task or Approval Event Handler](how-to-create-a-workflow-task-or-approval-event-handler.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

