---
title: ReleaseUpdateDB60_HRM.updateHcmCourseTypeGroup
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmCourseTypeGroup
ms:assetid: ccb54eb4-078d-a18d-8545-a36f098aea45
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719702(v=AX.60)
ms:contentKeyID: 49711268
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmCourseTypeGroup [AX 2012]


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
<td><p>updateHcmCourseTypeGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmCourseTypeGroup&lt;/c&gt; table from the &lt;c&gt;HRMCourseTypeGroup&lt;/c&gt; table.</p></td>
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
<td><p>HcmCourseTypeGroup</p></td>
</tr>
<tr class="even">
<td><p>HRMCourseTypeGroup</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will discard duplicate records if the \<c\>HrmCourseTypeGroupId\</c\> field and the \<c\>Description\</c\> field of the \<c\>HRMCourseTypeGroup\</c\> table are identical. The new unique identifier \<c\>CourseTypeGroupId\</c\> field of the \<c\>HcmCourseTypeGroup\</c\> table combines the \<c\>HrmCourseTypeGroupId\</c\> field and the \<c\>DataAreaId\</c\> field of the \<c\>HRMCourseTypeGroup\</c\> table from the first record found. All records found that are identified as duplicates in other companies will be discarded. If only one company exists, the \<c\>DataAreaId\</c\> field will not be appended.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMCourseTypeGroup</p></th>
<th><p>To Table: HcmCourseTypeGroup</p></th>
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
<td><p>HcmCourseTypeGroup</p></td>
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
<td><p>HRMCourseTypeGroup</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

