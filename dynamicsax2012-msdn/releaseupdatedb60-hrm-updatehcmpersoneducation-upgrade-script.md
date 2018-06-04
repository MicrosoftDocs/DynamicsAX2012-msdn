---
title: ReleaseUpdateDB60_HRM.updateHcmPersonEducation Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPersonEducation Upgrade Script
ms:assetid: 4acc0d65-200e-38b9-7858-a677a02143f6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685379(v=AX.60)
ms:contentKeyID: 49708072
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPersonEducation Upgrade Script 


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
<td><p>updateHcmPersonEducation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmPersonEducation table from the HRMVirtualNetworkEducation table.</p></td>
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
<td><p>ContactPerson</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
</tr>
<tr class="odd">
<td><p>HcmPersonEducation</p></td>
</tr>
<tr class="even">
<td><p>HRMApplicantTable</p></td>
</tr>
<tr class="odd">
<td><p>HRMEducationCenter</p></td>
</tr>
<tr class="even">
<td><p>HRMEducationDegree</p></td>
</tr>
<tr class="odd">
<td><p>HRMEducationType</p></td>
</tr>
<tr class="even">
<td><p>HRMVirtualNetworkEducation</p></td>
</tr>
<tr class="odd">
<td><p>HRMVirtualNetworkTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The Person field, which has the RecId value from the DirPerson table, replaces the HrmVirtualNetworkId field. The EducationDiscipline field, which has the RecId value from the HcmEducationDiscipline table, replaces the HrmEducationTypeId field. The EducationInstitution field, which has the RecId value from the HcmEducationInstitution table, replaces the HrmEducationCenterId field. The EducationLevel field, which has the RecId value from the HcmEducationLevel table, replaces the HrmEducationDegreeId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMVirtualNetworkEducation</p></th>
<th><p>To Table: HcmPersonEducation</p></th>
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
<td><p>HcmPersonEducation</p></td>
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
<td><p>HRMVirtualNetworkEducation</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

