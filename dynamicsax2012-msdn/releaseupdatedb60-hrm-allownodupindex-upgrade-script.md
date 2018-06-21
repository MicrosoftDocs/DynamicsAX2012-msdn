---
title: ReleaseUpdateDB60_HRM.allowNoDupIndex Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.allowNoDupIndex Upgrade Script
ms:assetid: db75a8a7-3f48-b09e-2c4a-de7cf2034144
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737190(v=AX.60)
ms:contentKeyID: 49711633
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.allowNoDupIndex Upgrade Script [AX 2012]


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
<td><p>allowNoDupIndex</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Resets the unique indexes on the HRM tables.</p></td>
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

The HcmWorker\_AK2 index of the HcmWorker table is reset. The IdIdx index of the HRMCourseInstructor table is reset. The IdIdx index of the HRMCourseTableInstructor table is reset. The CoursePersonIdx index of the HRMCourseAttendee table is reset. The IdIdx index of the HRMCourseAttendeeLine table is reset. The applicationIdx index of the HRMApplicantRouting table is reset. The groupIdIdx index of the HRMVirtualNetworkGroupRelation table is reset.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

