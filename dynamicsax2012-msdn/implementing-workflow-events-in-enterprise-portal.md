---
title: Implementing Workflow Events in Enterprise Portal
TOCTitle: Implementing Workflow Events in Enterprise Portal
ms:assetid: 6390369d-94a9-465e-bec2-dff38a2a5729
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677500(v=AX.60)
ms:contentKeyID: 35245350
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Implementing Workflow Events in Enterprise Portal 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AxWorkflowActionBar provides several events that can be used if you want to perform additional actions as a document is processed through a workflow for Enterprise Portal. These events are optional. They do not have to be used for a standard workflow implementation in Enterprise Portal. The following table lists the events that are available:

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
<td><p>EvaluatingCanSubmitToWorkflow</p></td>
<td><p>Occurs when the control attempts to determine whether the current record can be submitted to workflow.</p></td>
</tr>
<tr class="even">
<td><p>WorkflowConfigurationActive</p></td>
<td><p>Occurs after the control has loaded a configuration for the current record.</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowConfigurationLoading</p></td>
<td><p>Occurs when the control loads a configuration for the current record and after it has been determined that the record can be submitted to workflow.</p></td>
</tr>
<tr class="even">
<td><p>WorkflowSubmitCompleted</p></td>
<td><p>Occurs after the current record has been submitted to workflow.</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowWorkItemActionCompleted</p></td>
<td><p>Occurs after a work item for the current record has been completed.</p></td>
</tr>
<tr class="even">
<td><p>WorkflowWorkItemActive</p></td>
<td><p>Occurs after the control has retrieved a pending work item for the current user and current record.</p></td>
</tr>
</tbody>
</table>


## See also

[User Control Events](user-control-events.md)

