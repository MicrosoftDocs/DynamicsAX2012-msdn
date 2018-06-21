---
title: ReleaseUpdateDB60_HRM.updateHcmGoal Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmGoal Upgrade Script
ms:assetid: f4984154-0bc8-5907-d2ea-8afa24d5a907
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737549(v=AX.60)
ms:contentKeyID: 49712243
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmGoal Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHcmGoal</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmGoal table from the DEL_HRMGoal table.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>HcmGoal</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending the DataAreaId field to the GoalId field of the DEL\_HRMGoal table to create new, unique identifiers for the HcmGoal table when multiple companies exist. If only one company exists, the DataAreaId field will not be appended. The Worker field in the HcmGoal table is the foreign key to the HcmWorker table. The GoalType field in the HcmGoal table is the foreign key to the HcmGoalType table. The GoalHeading field in the HcmGoal table is the foreign key to the HcmGoalHeading table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRMGoal</p></th>
<th><p>To Table: HcmGoal</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>*</p></td>
<td><p>*</p></td>
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
<td><p>HcmGoal</p></td>
<td><p>*</p></td>
<td><p></p></td>
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
<td><p>DEL_HRMGoal</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

