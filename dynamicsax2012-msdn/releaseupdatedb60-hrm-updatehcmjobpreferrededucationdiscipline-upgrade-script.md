---
title: ReleaseUpdateDB60_HRM.updateHcmJobPreferredEducationDiscipline Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmJobPreferredEducationDiscipline Upgrade Script
ms:assetid: 846ac81d-a9e1-f36e-ae47-49fb15f35ce6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686009(v=AX.60)
ms:contentKeyID: 49709460
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmJobPreferredEducationDiscipline Upgrade Script 


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
<td><p>updateHcmJobPreferredEducationDiscipline</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts data into the HcmJobPreferredEducationDiscipline from the HRMJobEducationProfile table.</p></td>
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
<td><p>HcmJobPreferredEducationDiscipline</p></td>
</tr>
<tr class="even">
<td><p>DEL_HRMJobEducationProfile</p></td>
</tr>
<tr class="odd">
<td><p>HcmJob</p></td>
</tr>
<tr class="even">
<td><p>HRMEducationType</p></td>
</tr>
</tbody>
</table>


## Remarks

1.  The Job field which holds record ID from the HcmJob table replaces the Reference field.

2.  The EducationDiscipline field which holds record ID from the HcmEducationDiscipline table replaces the EducationTypeId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRMJobEducationProfile</p></th>
<th><p>To Table: HcmJobPreferredEducationDiscipline</p></th>
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
<td><p>HcmJobPreferredEducationDiscipline</p></td>
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

  


