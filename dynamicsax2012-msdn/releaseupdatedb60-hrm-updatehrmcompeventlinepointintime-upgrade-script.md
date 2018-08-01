---
title: ReleaseUpdateDB60_HRM.updateHRMCompEventLinePointInTime Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMCompEventLinePointInTime Upgrade Script
ms:assetid: 17a8d239-ada3-1c28-5f2e-59a8ccdf80ad
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718587(v=AX.60)
ms:contentKeyID: 49706870
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMCompEventLinePointInTime Upgrade Script 


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
<td><p>updateHRMCompEventLinePointInTime</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CompensationLevel and Worker, and Position fields in the HRMCompEventLinePointInTime table with the corresponding value from the record ID field in the HcmCompensationLevel table.</p></td>
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
<td><p>HRMCompEventLinePointInTime</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the CompensationLevel field in the HRMCompEventLinePointInTime table with the corresponding value from the record ID field in the HcmCompensationLevel table. Updates the Worker field in the HRMCompEventLinePointInTime table with the corresponding value from the record ID field in the HcmWorker table. Updates the Position field in the HRMCompEventLinePointInTime table with the corresponding value from the record ID field in the HcmPosition table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMCompEventLinePointInTime</p></th>
<th><p>To Table: HRMCompEventLinePointInTime</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_WorkerId</p></td>
<td><p>Worker</p></td>
</tr>
<tr class="even">
<td><p>del_PositionId</p></td>
<td><p>Position</p></td>
</tr>
<tr class="odd">
<td><p>del_LevelId</p></td>
<td><p>CompensationLevel</p></td>
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
<td><p>HRMCompEventLinePointInTime</p></td>
<td><p>Worker</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Position</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>CompensationLevel</p></td>
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
<td><p>HRMCompEventLinePointInTime</p></td>
<td><p>del_EmplId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>del_PositionId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>del_LevelId</p></td>
</tr>
</tbody>
</table>

  


