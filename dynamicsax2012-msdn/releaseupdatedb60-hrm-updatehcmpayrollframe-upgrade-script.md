---
title: ReleaseUpdateDB60_HRM.updateHcmPayrollFrame Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPayrollFrame Upgrade Script
ms:assetid: 9cc58385-ad1f-2123-ac4d-61c43a36b923
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686349(v=AX.60)
ms:contentKeyID: 49710051
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPayrollFrame Upgrade Script 


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
<td><p>updateHcmPayrollFrame</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmPayrollFrame table from the HRMPayrollFrame table.</p></td>
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
<td><p>HcmPayrollFrame</p></td>
</tr>
<tr class="even">
<td><p>HRMEmplCategory</p></td>
</tr>
<tr class="odd">
<td><p>HRMPayrollFrame</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending the DataAreaId to the HrmEmplPayrollFrameId field of the HRMPayrollFrame table to create new, unique identifiers for the HcmPayrollFrame table when multiple companies exist. If only one company exists, the DataAreaId field will not be appended. The PayrollFrameCategory field in the HcmPayrollFrame table is the foreign key to the HcmPayrollFrameCategory table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMPayrollFrame</p></th>
<th><p>To Table: HcmPayrollFrame</p></th>
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
<td><p>HcmPayrollFrame</p></td>
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
<td><p>HRMPayrollFrame</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


