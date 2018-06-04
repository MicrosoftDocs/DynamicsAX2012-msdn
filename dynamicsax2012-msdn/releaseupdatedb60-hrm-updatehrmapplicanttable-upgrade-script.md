---
title: ReleaseUpdateDB60_HRM.updateHRMApplicantTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMApplicantTable Upgrade Script
ms:assetid: 98164ae0-9718-f37f-c01c-3a86dafcef6c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686235(v=AX.60)
ms:contentKeyID: 49709938
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMApplicantTable Upgrade Script 


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
<td><p>updateHRMApplicantTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Person field of the HRMApplicantTable table with the corresponding value from the RecId field of the DirPerson table. Create an DirPerson record when the person does not exist. Updates the EducationLevel field of the HRMApplicantTable table with the corresponding value from the RecId field of the Hcm table. Updates the VeteranStatus field of the HRMApplicantTable table with the corresponding value from the RecId field of the HcmVeteranStatus table. Updates the EthnicOrigin field of the HRMApplicantTable table with the corresponding value from the RecId field of the HcmEthnicOrigin table.</p></td>
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
<td><p>DirParameters</p></td>
</tr>
<tr class="even">
<td><p>DirPartyTable</p></td>
</tr>
<tr class="odd">
<td><p>DirPerson</p></td>
</tr>
<tr class="even">
<td><p>DirPersonName</p></td>
</tr>
<tr class="odd">
<td><p>HRMApplicantTable</p></td>
</tr>
<tr class="even">
<td><p>HRMEducationDegree</p></td>
</tr>
<tr class="odd">
<td><p>HRMEthnicOrigin</p></td>
</tr>
<tr class="even">
<td><p>HRMVeteranStatus</p></td>
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
<th><p>From Table:</p></th>
<th><p>To Table: HRMApplicantTable</p></th>
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
<td><p>HRMApplicantTable</p></td>
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
<td><p></p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

