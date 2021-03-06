﻿---
title: ReleaseUpdateDB60_HRM.updateHcmCourseTypeGroup Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmCourseTypeGroup Upgrade Script
ms:assetid: dd3d0197-3136-402a-5e12-1618b3cd2917
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737207(v=AX.60)
ms:contentKeyID: 49711650
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmCourseTypeGroup Upgrade Script 


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
<td><p>updateHcmCourseTypeGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmCourseTypeGroup table from the HRMCourseTypeGroup table.</p></td>
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

This upgrade will discard duplicate records if the HrmCourseTypeGroupId field and the Description field of the HRMCourseTypeGroup table are identical. The new unique identifier CourseTypeGroupId field of the HcmCourseTypeGroup table combines the HrmCourseTypeGroupId field and the DataAreaId field of the HRMCourseTypeGroup table from the first record found. All records found that are identified as duplicates in other companies will be discarded. If only one company exists, the DataAreaId field will not be appended.

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

  


