---
title: ReleaseUpdateDB60_HRM.updateHcmEducationDisciplineGroup Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmEducationDisciplineGroup Upgrade Script
ms:assetid: f3523452-ab55-6885-1a1c-7ebdfdea940d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737509(v=AX.60)
ms:contentKeyID: 49712203
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmEducationDisciplineGroup Upgrade Script 


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
<td><p>updateHcmEducationDisciplineGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmEducationDisciplineGroup table from the HRMEducationGroupType table.</p></td>
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
<td><p>HcmEducationDisciplineGroup</p></td>
</tr>
<tr class="even">
<td><p>HRMEducationGroup</p></td>
</tr>
<tr class="odd">
<td><p>HRMEducationGroupType</p></td>
</tr>
<tr class="even">
<td><p>HRMEducationType</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will discard duplicates associated with discard duplicates upgrades with the HcmEducationDisciplineGroup table and the HcmEducationDisciplineCategory table. The EducationDiscipline field in the HcmEducationDisciplineGroup table is the foreign key to the HcmEducationDiscipline table. The EducationDisciplineCategory field in the HcmEducationDisciplineGroup table is the foreign key to the HcmEducationDisciplineCategory table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMEducationGroupType</p></th>
<th><p>To Table: HcmEducationDisciplineGroup</p></th>
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
<td><p>HcmEducationDisciplineGroup</p></td>
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
<td><p>HRMEducationGroupType</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


