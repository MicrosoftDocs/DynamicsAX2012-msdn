---
title: ReleaseUpdateDB60_HRM.updateHcmPersonProfessionalExperience Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPersonProfessionalExperience Upgrade Script
ms:assetid: fc2f4679-6cf1-09cd-2559-85c212753f5f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720142(v=AX.60)
ms:contentKeyID: 49712447
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPersonProfessionalExperience Upgrade Script 


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
<td><p>updateHcmPersonProfessionalExperience</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmPersonProfessionalExperience table from the HRMVirtualNetworkQualification table.</p></td>
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
<td><p>HcmPersonProfessionalExperience</p></td>
</tr>
<tr class="even">
<td><p>HRMApplicantTable</p></td>
</tr>
<tr class="odd">
<td><p>HRMVirtualNetworkQualification</p></td>
</tr>
<tr class="even">
<td><p>HRMVirtualNetworkTable</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsLocation</p></td>
</tr>
</tbody>
</table>


## Remarks

The Person field holding the RecId value from the DirPerson table replaces the HrmVirtualNetworkId field. The EmployerLocationURL field holding RecId value from the LogisticsLocation table replaces field URL field. The EmployerLocationTelephone field holding the RecId value from the LogisticsLocation table replaces the Phone field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMVirtualNetworkQualification</p></th>
<th><p>To Table: HcmPersonProfessionalExperience</p></th>
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
<td><p>HcmPersonProfessionalExperience</p></td>
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
<td><p>HRMVirtualNetworkQualification</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


