---
title: ReleaseUpdateDB60_Lean.updateKanbanJobs Upgrade Script
TOCTitle: ReleaseUpdateDB60_Lean.updateKanbanJobs Upgrade Script
ms:assetid: 23abf7b9-85b6-4757-d135-2cfefe27b9f2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684976(v=AX.60)
ms:contentKeyID: 49707178
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Lean.updateKanbanJobs Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Lean</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateKanbanJobs</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the KanbanJob table with the records created based on the DEL_KanbanMapping table data.</p></td>
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
<td><p>Lean Manufacturing</p></td>
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
<td><p>KanbanJob</p></td>
</tr>
<tr class="even">
<td><p>KanbanJobPickingList</p></td>
</tr>
<tr class="odd">
<td><p>Kanban</p></td>
</tr>
<tr class="even">
<td><p>DEL_KanbanMapping</p></td>
</tr>
<tr class="odd">
<td><p>DEL_KanbanRuleMapping</p></td>
</tr>
<tr class="even">
<td><p>KanbanRule</p></td>
</tr>
<tr class="odd">
<td><p>KanbanFlow</p></td>
</tr>
<tr class="even">
<td><p>LeanProductionFlowActivity</p></td>
</tr>
<tr class="odd">
<td><p>LeanScheduleGroup</p></td>
</tr>
<tr class="even">
<td><p>LeanScheduleGroupItem</p></td>
</tr>
<tr class="odd">
<td><p>PlanActivity</p></td>
</tr>
<tr class="even">
<td><p>PlanPlanActivity</p></td>
</tr>
<tr class="odd">
<td><p>PlanReference</p></td>
</tr>
<tr class="even">
<td><p>InventDim</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
</tr>
<tr class="even">
<td><p>DataArea</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

