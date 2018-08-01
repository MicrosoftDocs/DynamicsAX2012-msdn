---
title: ReleaseUpdateDB60_HRM.allowDupIndex Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.allowDupIndex Upgrade Script
ms:assetid: 2f9aa560-7f5f-f48a-d11b-d71586ceca71
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736034(v=AX.60)
ms:contentKeyID: 49707449
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.allowDupIndex Upgrade Script [AX 2012]


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
<td><p>allowDupIndex</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Disable the unique indexes on the HRM tables to allow for duplicate IDs.</p></td>
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
<td><p>HcmWorker</p></td>
</tr>
<tr class="even">
<td><p>HRMCourseInstructor</p></td>
</tr>
<tr class="odd">
<td><p>HRMCourseTableInstructor</p></td>
</tr>
<tr class="even">
<td><p>HRMCourseAttendee</p></td>
</tr>
<tr class="odd">
<td><p>HRMCourseAttendeeLine</p></td>
</tr>
<tr class="even">
<td><p>HRMApplicantRouting</p></td>
</tr>
<tr class="odd">
<td><p>HRMVirtualNetworkGroupRelation</p></td>
</tr>
<tr class="even">
<td><p>SysInfoLog</p></td>
</tr>
</tbody>
</table>


## Remarks

The HcmWorker\_AK2 index of the HcmWorker table is disabled. The IdIdx index of the HRMCourseInstructor table is disabled. The IdIdx index of the HRMCourseTableInstructor table is disabled. The CoursePersonIdx index of the HRMCourseAttendee table is disabled. The IdIdx index of the HRMCourseAttendeeLine table is disabled. The applicationIdx index of the HRMApplicantRouting table is disabled. The groupIdIdx index of the HRMVirtualNetworkGroupRelation table is disabled.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

