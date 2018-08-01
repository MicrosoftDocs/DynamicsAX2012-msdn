---
title: ReleaseUpdateDB60_Lean.createLeanScheduleGroupsItems Upgrade Script
TOCTitle: ReleaseUpdateDB60_Lean.createLeanScheduleGroupsItems Upgrade Script
ms:assetid: 2855f96a-1baa-8fcd-c438-b213beef0772
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735865(v=AX.60)
ms:contentKeyID: 49707283
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Lean.createLeanScheduleGroupsItems Upgrade Script 


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
<td><p>createLeanScheduleGroupsItems</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the LeanScheduleGroupItem and LeanScheduleGroupEntrySingle tables with the records created based on the DEL_KanbanRuleProductFamily table data.</p></td>
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
<td><p>DEL_KanbanRuleProductFamily</p></td>
</tr>
<tr class="even">
<td><p>LeanScheduleGroup</p></td>
</tr>
<tr class="odd">
<td><p>LeanScheduleGroupItem</p></td>
</tr>
<tr class="even">
<td><p>LeanScheduleGroupEntrySingle</p></td>
</tr>
<tr class="odd">
<td><p>DataArea</p></td>
</tr>
</tbody>
</table>

  


