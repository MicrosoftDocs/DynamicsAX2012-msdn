---
title: ReleaseUpdateDB60_HRM.allowDupIndex
TOCTitle: ReleaseUpdateDB60_HRM.allowDupIndex
ms:assetid: fb90bfc5-49d0-2a50-daae-7315e3b6ef75
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720124(v=AX.60)
ms:contentKeyID: 49712429
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.allowDupIndex 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>Disable the unique indexes on the HRM tables to allow duplicate ids.</p></td>
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

The index \<c\>HcmWorker\_AK2\</c\> of the \<c\>HcmWorker\</c\> table is disabled. The index \<c\>IdIdx\</c\> of the \<c\>HRMCourseInstructor\</c\> table is disabled. The index \<c\>IdIdx\</c\> of the \<c\>HRMCourseTableInstructor\</c\> table is disabled. The index \<c\>CoursePersonIdx\</c\> of the \<c\>HRMCourseAttendee\</c\> table is disabled. The index \<c\>IdIdx\</c\> of the \<c\>HRMCourseAttendeeLine\</c\> table is disabled. The index \<c\>applicationIdx\</c\> of the \<c\>HRMApplicantRouting\</c\> table is disabled. The index \<c\>groupIdIdx\</c\> of the \<c\>HRMVirtualNetworkGroupRelation\</c\> table is disabled.

  


