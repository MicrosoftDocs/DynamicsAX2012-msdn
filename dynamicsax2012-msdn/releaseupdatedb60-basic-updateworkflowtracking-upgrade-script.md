---
title: ReleaseUpdateDB60_Basic.updateWorkflowTracking Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateWorkflowTracking Upgrade Script
ms:assetid: e6e72a74-4ea9-048a-1bb1-717d500a6aad
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719813(v=AX.60)
ms:contentKeyID: 49711886
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateWorkflowTracking Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateWorkflowTracking</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This upgrade scripts normalizes the data in the WorkflowTrackingStatusTable and the WorkflowTrackingTable tables. Redundant data will be removed, an additional table is being added, and surrogate keys are being introduced.</p></td>
</tr>
</tbody>
</table>


## Affected Modules and Tables

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Modules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Basic</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Tables</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkflowTrackingStatusTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingCommentTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingArgumentTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingWorkItem</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WorkflowTrackingTable</p></th>
<th><p>To Table: WorkflowTrackingWorkItem</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ToUser</p></td>
<td><p>ToUser</p></td>
</tr>
<tr class="even">
<td><p>WorkItemSubject</p></td>
<td><p>WorkItemSubject</p></td>
</tr>
<tr class="odd">
<td><p>DueDateTime</p></td>
<td><p>DueDateTime</p></td>
</tr>
<tr class="even">
<td><p>Outcome</p></td>
<td><p>Outcome</p></td>
</tr>
<tr class="odd">
<td><p>WorkItemId</p></td>
<td><p>WorkItemId</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkflowTrackingWorkItem</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>WorkflowTrackingStatusTable</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>WorkflowElementTable</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>WorkflowStepTable</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>WorkflowParallelBranchTable</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>WorkflowSubWorkflow</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingCommentTable</p></td>
<td><p>WorkflowTrackingTable</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingArgumentTable</p></td>
<td><p>WorkflowTrackingCommentTable</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkflowTrackingStatusTable</p></td>
<td><p>ConfigurationId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingStatusTable</p></td>
<td><p>SubWorkflowActivityId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>ContextCompanyId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>ContextTableId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>ContextRecId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>CorrelationId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>ConfigurationId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>ElementId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>StepId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>WorkItemId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>WorkItemActivityInstanceId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>DueDateTime</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>Outcome</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>ToUser</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>WorkItemSubject</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>RootCorrelationId</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>ParentCorrelationId</p></td>
</tr>
<tr class="even">
<td><p>WorkflowTrackingTable</p></td>
<td><p>SubWorkflowSequence</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowTrackingTable</p></td>
<td><p>SubWorkflowId</p></td>
</tr>
</tbody>
</table>

  


