---
title: ReleaseUpdateDB60_HRM.updateHcmGoalComment Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmGoalComment Upgrade Script
ms:assetid: 7674929e-f206-6b03-fdc0-baddabd79a91
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719335(v=AX.60)
ms:contentKeyID: 49709125
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmGoalComment Upgrade Script 


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
<td><p>updateHcmGoalComment</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmGoalComment table from the HRMGoalComment table.</p></td>
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
<td><p>EmplTable</p></td>
</tr>
<tr class="even">
<td><p>HcmGoalComment</p></td>
</tr>
<tr class="odd">
<td><p>HcmWorker</p></td>
</tr>
<tr class="even">
<td><p>HRMGoal</p></td>
</tr>
<tr class="odd">
<td><p>HRMGoalComment</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The Worker field in the HcmGoalComment table is the foreign key to the HcmWorker table. The Goal field in the HcmGoalComment table is the foreign key to the HcmGoal table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMGoalComment</p></th>
<th><p>To Table: HcmGoalComment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<td><p>HcmGoalComment</p></td>
<td><p></p></td>
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
<td><p>HRMGoalComment</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


