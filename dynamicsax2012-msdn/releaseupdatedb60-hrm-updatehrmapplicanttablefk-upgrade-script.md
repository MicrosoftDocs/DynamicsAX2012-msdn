---
title: ReleaseUpdateDB60_HRM.updateHRMApplicantTableFK Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMApplicantTableFK Upgrade Script
ms:assetid: 54a3b06e-8c56-7fa8-e351-dfb6fbc7bb9d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736148(v=AX.60)
ms:contentKeyID: 49708324
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMApplicantTableFK Upgrade Script 


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
<td><p>updateHRMApplicantTableFK</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EducationLevel field, the VeteranStatus field, and the EthnicOrigin field of the HRMApplicantTable table.</p></td>
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
<td><p>HRMEducationDegree</p></td>
</tr>
<tr class="even">
<td><p>HRMVeteranStatus</p></td>
</tr>
<tr class="odd">
<td><p>HRMEthnicOrigin</p></td>
</tr>
<tr class="even">
<td><p>HRMApplicantTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the EducationLevel field of the HRMApplicantTable table with the corresponding value from the RecId field of the HcmEducationLevel table. Updates the VeteranStatus field of the HRMApplicantTable table with the corresponding value from the RecId field of the HcmVeteranStatus table. Updates the EthnicOrigin field of the HRMApplicantTable table with the corresponding value from the RecId field of the HcmEthnicOrigin table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMEducationDegree</p></th>
<th><p>To Table: HRMApplicantTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_MappingRecId</p></td>
<td><p>EducationLevel</p></td>
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
<th><p>From Table: HRMVeteranStatus</p></th>
<th><p>To Table: HRMApplicantTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_MappingRecId</p></td>
<td><p>VeteranStatus</p></td>
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
<th><p>From Table: HRMEthnicOrigin</p></th>
<th><p>To Table: HRMApplicantTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_MappingRecId</p></td>
<td><p>EthnicOrigin</p></td>
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
<td><p>HRMApplicantTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

