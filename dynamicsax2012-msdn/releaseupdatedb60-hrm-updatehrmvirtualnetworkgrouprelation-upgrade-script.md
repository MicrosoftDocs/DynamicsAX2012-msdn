---
title: ReleaseUpdateDB60_HRM.updateHRMVirtualNetworkGroupRelation Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMVirtualNetworkGroupRelation Upgrade Script
ms:assetid: e4c93a4e-5a09-4262-372e-1ca09310fef4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737379(v=AX.60)
ms:contentKeyID: 49711820
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMVirtualNetworkGroupRelation Upgrade Script 


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
<td><p>updateHRMVirtualNetworkGroupRelation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Person field of the HrmVirtualNetworkGroupRelation table with the corresponding value from the RecId field of the DirPerson table.</p></td>
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
<td><p>HRMVirtualNetworkGroupRelation</p></td>
</tr>
<tr class="even">
<td><p>HRMVirtualNetworkTable</p></td>
</tr>
<tr class="odd">
<td><p>EmplTable</p></td>
</tr>
<tr class="even">
<td><p>ContactPerson</p></td>
</tr>
<tr class="odd">
<td><p>DEL_HRMApplicantTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The Person field, which has RecId value from the DirPerson table, replaces the HrmVirtualNetworkId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: HRMVirtualNetworkGroupRelation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Party</p></td>
<td><p>Person</p></td>
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
<th><p>From Table: HRMApplicant</p></th>
<th><p>To Table: HRMVirtualNetworkGroupRelation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Person</p></td>
<td><p>Person</p></td>
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
<th><p>From Table: ContactPerson</p></th>
<th><p>To Table: HRMVirtualNetworkGroupRelation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Party</p></td>
<td><p>Person</p></td>
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
<td><p>HRMVirtualNetworkGroupRelation</p></td>
<td><p>Person</p></td>
<td><p>HcmPersonRecId</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name:</p></th>
<th><p>New Table Name:</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>HRMVirtualNetworkId</p></td>
<td><p>DEL_HRMVirtualNetworkId</p></td>
</tr>
</tbody>
</table>

  


