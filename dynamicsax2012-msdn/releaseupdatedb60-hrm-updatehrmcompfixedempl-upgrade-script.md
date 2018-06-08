---
title: ReleaseUpdateDB60_HRM.updateHRMCompFixedEmpl Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMCompFixedEmpl Upgrade Script
ms:assetid: 305f9e3f-f423-b3f7-cc86-db302d82c695
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736059(v=AX.60)
ms:contentKeyID: 49707474
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMCompFixedEmpl Upgrade Script 


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
<td><p>updateHRMCompFixedEmpl</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the DefaultDimension, Worker, and Position fields in the HRMCompFixedEmpl table.</p></td>
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
<td><p>HRMCompFixedEmpl</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the DefaultDimension field in the HRMCompFixedEmpl table with the value that corresponds from the RecId field in the DimensionAttributeValueSet table. Updates the Worker field in the HRMCompFixedEmpl table with the values that correspond from the RecId field in the HcmWorker table. Updates the Position field in the HRMCompFixedEmpl table with the value that corresponds from the RecId field in the HcmPosition table.

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
<td><p>HRMCompFixedEmpl</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Worker</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Position</p></td>
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
<td><p>HRMCompFixedEmpl</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>del_EmplId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>del_PositionId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

