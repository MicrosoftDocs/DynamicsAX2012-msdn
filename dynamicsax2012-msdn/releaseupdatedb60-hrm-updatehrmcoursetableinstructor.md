---
title: ReleaseUpdateDB60_HRM.updateHRMCourseTableInstructor
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMCourseTableInstructor
ms:assetid: aa3e0124-3ade-8903-c731-a9c1d8793c12
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686436(v=AX.60)
ms:contentKeyID: 49710392
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMCourseTableInstructor 


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
<td><p>updateHRMCourseTableInstructor</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the &lt;c&gt;CourseInstructor&lt;/c&gt; field of the &lt;c&gt;HrmCourseTableInstructor&lt;/c&gt; table with the corresponding value from the &lt;c&gt;RecId&lt;/c&gt; field of the &lt;c&gt;HrmCourseInstructor&lt;/c&gt; table.</p></td>
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
<td><p>HRMCourseInstructor</p></td>
</tr>
<tr class="even">
<td><p>HRMCourseTableInstructor</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>CourseInstructor\</c\> field hoding RecId of the \<c\>HrmCourseInstructor\</c\> table replaces the \<c\>HrmCourseInstructorId\</c\> field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HrmCourseInstructor</p></th>
<th><p>To Table: HRMCourseTableInstructor</p></th>
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
<td><p>HRMCourseTableInstructor</p></td>
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
<td><p>HrmCourseInstructor</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


