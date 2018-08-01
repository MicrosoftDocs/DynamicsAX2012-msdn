---
title: ReleaseUpdateDB60_HRM.updateHcmJobResponsibility Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmJobResponsibility Upgrade Script
ms:assetid: 1857b7b8-5dc6-539e-cfe1-380f25d00c5f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718605(v=AX.60)
ms:contentKeyID: 49706889
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmJobResponsibility Upgrade Script 


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
<td><p>updateHcmJobResponsibility</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts data into the HcmJobResponsibility table from the DEL_HRMJobResponsibility table.</p></td>
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
<td><p>HcmJobResponsibility</p></td>
</tr>
<tr class="even">
<td><p>DEL_HRMJobResponsibility</p></td>
</tr>
<tr class="odd">
<td><p>DEL_HRMResponsibility</p></td>
</tr>
<tr class="even">
<td><p>HcmJob</p></td>
</tr>
</tbody>
</table>


## Remarks

1.  The Job field which holds record ID from the HcmJob table replaces the Reference field.

2.  The Responsibility field which holds record ID from the HcmResponsibility table replaces the ResponsibilityId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRMJobResponsibility</p></th>
<th><p>To Table: HcmJobResponsibility</p></th>
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
<td><p>HcmJobResponsibility</p></td>
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
<td><p>DEL_HRMJobResponsibility</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


