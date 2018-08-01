---
title: ReleaseUpdateDB60_HRM.updateHcmWorkerGroup_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmWorkerGroup_RU Upgrade Script
ms:assetid: e18b4d2e-1003-3ca3-998e-9dc57dda0f75
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737321(v=AX.60)
ms:contentKeyID: 49711764
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmWorkerGroup\_RU Upgrade Script 


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
<td><p>updateHcmWorkerGroup_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records in the HcmWorkerGroup_RU table from the EmplGroup_RU table.</p></td>
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
<td><p>HcmWorkerGroup_RU</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will discard duplicate records if the EmplGroupId field of the EmplGroup\_RU table is identical.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplGroup_RU</p></th>
<th><p>To Table: HcmWorkerGroup_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EmplGroupId</p></td>
<td><p>WorkerGroupId</p></td>
</tr>
<tr class="even">
<td><p>Description</p></td>
<td><p>Description</p></td>
</tr>
<tr class="odd">
<td><p>del_OffsetLedgerAccount</p></td>
<td><p>OffsetLedgerDimension</p></td>
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
<td><p>HcmWorkerGroup_RU</p></td>
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
<td><p>EmplGroup_RU</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


