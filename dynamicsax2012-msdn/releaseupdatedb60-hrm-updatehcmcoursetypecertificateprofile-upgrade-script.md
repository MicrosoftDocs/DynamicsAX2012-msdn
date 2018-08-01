---
title: ReleaseUpdateDB60_HRM.updateHcmCourseTypeCertificateProfile Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmCourseTypeCertificateProfile Upgrade Script
ms:assetid: e427ab5c-4698-7f7a-367f-cbe530ca8256
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737389(v=AX.60)
ms:contentKeyID: 49711830
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmCourseTypeCertificateProfile Upgrade Script [AX 2012]


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
<td><p>updateHcmCourseTypeCertificateProfile</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmCourseTypeCertificateProfile table from the HRMCourseTypeCertificateProfile table.</p></td>
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
<td><p>HcmCourseType</p></td>
</tr>
<tr class="even">
<td><p>HcmCourseTypeCertificateProfile</p></td>
</tr>
<tr class="odd">
<td><p>HRMCertificateType</p></td>
</tr>
<tr class="even">
<td><p>HRMCourseTypeCertificateProfile</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The CourseType field in the HcmCourseTypeCertificateProfile table is the foreign key to the HcmCourseType table. The CertificateType field in the HcmCourseTypeCertificateProfile table is the foreign key to the HcmCertificateType table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMCourseTypeCertificateProfile</p></th>
<th><p>To Table: HcmCourseTypeCertificateProfile</p></th>
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
<td><p>HcmCourseTypeCertificateProfile</p></td>
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
<td><p>HRMCourseTypeCertificateProfile</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

