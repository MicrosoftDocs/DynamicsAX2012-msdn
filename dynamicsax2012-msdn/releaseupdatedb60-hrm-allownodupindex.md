---
title: ReleaseUpdateDB60_HRM.allowNoDupIndex
TOCTitle: ReleaseUpdateDB60_HRM.allowNoDupIndex
ms:assetid: c8e23853-b39f-636d-f54b-4b48b5995ac3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719600(v=AX.60)
ms:contentKeyID: 49711167
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.allowNoDupIndex 


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
<td><p>allowNoDupIndex</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Reset the unique indexes on the HRM tables.</p></td>
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

The index \<c\>HcmWorker\_AK2\</c\> of the \<c\>HcmWorker\</c\> table is reset. The index \<c\>IdIdx\</c\> of the \<c\>HRMCourseInstructor\</c\> table is reset. The index \<c\>IdIdx\</c\> of the \<c\>HRMCourseTableInstructor\</c\> table is reset. The index \<c\>CoursePersonIdx\</c\> of the \<c\>HRMCourseAttendee\</c\> table is reset. The index \<c\>IdIdx\</c\> of the \<c\>HRMCourseAttendeeLine\</c\> table is reset. The index \<c\>applicationIdx\</c\> of the \<c\>HRMApplicantRouting\</c\> table is reset. The index \<c\>groupIdIdx\</c\> of the \<c\>HRMVirtualNetworkGroupRelation\</c\> table is reset.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

