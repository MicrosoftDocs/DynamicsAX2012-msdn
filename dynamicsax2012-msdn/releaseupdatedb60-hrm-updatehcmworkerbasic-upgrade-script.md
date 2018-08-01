---
title: ReleaseUpdateDB60_HRM.updateHcmWorkerBasic Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmWorkerBasic Upgrade Script
ms:assetid: 075f0e45-31f9-5c0d-30ef-244e67820c6f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684760(v=AX.60)
ms:contentKeyID: 49706456
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmWorkerBasic Upgrade Script 


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
<td><p>updateHcmWorkerBasic</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmWorker table, the HcmPersonnelNumber table, the HcmEmployeeAffiliation table, and the HcmContractorAffiliation table from the EmplTable table.</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
</tr>
<tr class="odd">
<td><p>HcmContractorAffiliation</p></td>
</tr>
<tr class="even">
<td><p>HcmEmployeeAffiliation</p></td>
</tr>
<tr class="odd">
<td><p>HcmPersonnelNumber</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
</tr>
<tr class="odd">
<td><p>HRMPartyEmployeeRelationship</p></td>
</tr>
</tbody>
</table>


## Remarks

The Person field in the HcmWorker table is the foreign key to the DirPerson table. The Worker field in the HcmPersonnelNumber table is the foreign key to the HcmWorker table. The Worker field in the HcmEmployeeAffiliation table is the foreign key to the HcmWorker table. The Worker field in the HcmContractorAffiliation table is the foreign key to the HcmWorker table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: HcmWorker</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: HcmPersonnelNumber</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: HcmEmployeeAffiliation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: HcmContractorAffiliation</p></th>
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
<td><p>HcmWorker</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>HcmPersonnelNumber</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>HcmEmployeeAffiliation</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>HcmContractorAffiliation</p></td>
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
<td><p>EmplTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


