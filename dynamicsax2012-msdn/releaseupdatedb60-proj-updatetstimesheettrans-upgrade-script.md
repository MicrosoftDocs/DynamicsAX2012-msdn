---
title: ReleaseUpdateDB60_Proj.updateTSTimesheetTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateTSTimesheetTrans Upgrade Script
ms:assetid: c540e6fe-e00e-f8fd-0957-c99bce42858c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719524(v=AX.60)
ms:contentKeyID: 49711092
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateTSTimesheetTrans Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateTSTimesheetTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TSTimesheetTrans table by using the new SFK field from the TSTimesheetLineWeek table that is based on the refactoring done in Microsoft Dynamics AX 2012.</p></td>
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
<td><p>Project</p></td>
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
<td><p>TSTimesheetTrans</p></td>
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
<td><p>TSTimesheetTrans</p></td>
<td><p>TSTimesheetLineWeek</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>

  


