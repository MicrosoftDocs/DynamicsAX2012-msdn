---
title: ReleaseUpdateDB60_HRM.updateHcmEmploymentContractor Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmEmploymentContractor Upgrade Script
ms:assetid: 187499a4-0e7e-5f4b-8b85-7e9a083aea74
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718606(v=AX.60)
ms:contentKeyID: 49706890
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmEmploymentContractor Upgrade Script 


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
<td><p>updateHcmEmploymentContractor</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmEmploymentContractor table from the HRMPartyEmployeeRelationship table and the VendTable table.</p></td>
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
<td><p>HcmEmploymentContractor</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMPartyEmployeeRelationship</p></th>
<th><p>To Table: HcmEmploymentContractor</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ValidFromDateTime</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="even">
<td><p>ValidToDateTime</p></td>
<td><p>ValidTo</p></td>
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
<th><p>From Table: HcmEmployment</p></th>
<th><p>To Table: HcmEmploymentContractor</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ReId</p></td>
<td><p>Employment</p></td>
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
<th><p>From Table: VendTable</p></th>
<th><p>To Table: HcmEmploymentContractor</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountNum</p></td>
<td><p>VendorId</p></td>
</tr>
<tr class="even">
<td><p>DataAreaId</p></td>
<td><p>VendorDataAreaId</p></td>
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
<td><p>HcmEmploymentContractor</p></td>
<td><p>*</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


