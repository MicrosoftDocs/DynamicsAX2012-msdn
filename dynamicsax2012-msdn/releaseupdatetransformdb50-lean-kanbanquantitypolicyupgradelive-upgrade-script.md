---
title: ReleaseUpdateTransformDB50_Lean.kanbanQuantityPolicyUpgradeLive Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Lean.kanbanQuantityPolicyUpgradeLive Upgrade Script
ms:assetid: afb90198-19e3-6ed7-8728-b0c79275b44a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686587(v=AX.60)
ms:contentKeyID: 49710541
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Lean.kanbanQuantityPolicyUpgradeLive Upgrade Script [AX 2012]


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
<td><p>kanbanQuantityPolicyUpgradeLive</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the KanbanQuantityPolicyUpgrade table with the records that are created based on the EBCKanbanGroup table data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
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
<td><p>KanbanQuantityPolicyUpgrade</p></td>
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
<th><p>From Table: EBCKanBanGroup</p></th>
<th><p>To Table: KanbanQuantityPolicyUpgrade</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AlphaFactor</p></td>
<td><p>AlphaFactor</p></td>
</tr>
<tr class="even">
<td><p>BackwardHorizon</p></td>
<td><p>BackwardHorizon</p></td>
</tr>
<tr class="odd">
<td><p>ForwardHorizon</p></td>
<td><p>ForwardHorizon</p></td>
</tr>
<tr class="even">
<td><p>FormulaType</p></td>
<td><p>FormulaType</p></td>
</tr>
<tr class="odd">
<td><p>KanBanGroupId</p></td>
<td><p>KanbanGroupId</p></td>
</tr>
<tr class="even">
<td><p>Level</p></td>
<td><p>Level</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: InventTable</p></th>
<th><p>To Table: KanbanQuantityPolicyUpgrade</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ItemId</p></td>
<td><p>ItemId</p></td>
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
<td><p>KanbanQuantityPolicyUpgrade</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

