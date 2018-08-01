---
title: ReleaseUpdateTransformDB50_Lean.validateKanbanRulesDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Lean.validateKanbanRulesDelta Upgrade Script
ms:assetid: 57e2d080-fbf7-a83e-3e8a-da081e69e7d9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736221(v=AX.60)
ms:contentKeyID: 49708397
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Lean.validateKanbanRulesDelta Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Lean</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateKanbanRulesDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Provides validation of Kanban rules mappings and runs as a delta script to perform mandatory critical validations before going to the single user mode.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Manufacture</p></td>
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
<td><p>KanbanRuleMapping</p></td>
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
<td><p>KanbanRuleMapping</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>KanbanRuleProductFamily</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>KanbanRule</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>KanbanFlow</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PlanPlanActivity</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PlanActivity</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PlanActivityRelationship</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


