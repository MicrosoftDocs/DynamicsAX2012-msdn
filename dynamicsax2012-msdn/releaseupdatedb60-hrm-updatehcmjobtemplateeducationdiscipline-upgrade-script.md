---
title: ReleaseUpdateDB60_HRM.updateHcmJobTemplateEducationDiscipline Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmJobTemplateEducationDiscipline Upgrade Script
ms:assetid: 6acc46eb-4af4-208a-8cd6-cc050baddc5e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685662(v=AX.60)
ms:contentKeyID: 49708864
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmJobTemplateEducationDiscipline Upgrade Script 


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
<td><p>updateHcmJobTemplateEducationDiscipline</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts data into the HcmJobTemplateEducationDiscipline table from the DEL_HRMJobEducationProfile table.</p></td>
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
<td><p>HcmJobTemplateEducationDiscipline</p></td>
</tr>
<tr class="even">
<td><p>DEL_HRMJobEducationProfile</p></td>
</tr>
<tr class="odd">
<td><p>HRMEducationType</p></td>
</tr>
<tr class="even">
<td><p>HcmJobTemplate</p></td>
</tr>
</tbody>
</table>


## Remarks

1.  The JobTemplate field, which holds a record ID from the HcmJobTemplate table, replaces the Reference field.

2.  The EducationDiscipline field, which holds a record ID from the HcmEducationDiscipline table, replaces the EducationTypeId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRMJobEducationProfile</p></th>
<th><p>To Table: HcmJobTemplateEducationDiscipline</p></th>
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
<td><p>HcmJobTemplateEducationDiscipline</p></td>
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
<td><p>DEL_HRMJobEducationProfile</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


