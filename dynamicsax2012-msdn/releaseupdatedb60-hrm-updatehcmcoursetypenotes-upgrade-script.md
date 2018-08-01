﻿---
title: ReleaseUpdateDB60_HRM.updateHcmCourseTypeNotes Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmCourseTypeNotes Upgrade Script
ms:assetid: 997454bf-2eae-4419-9350-be5066b7fbe3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686274(v=AX.60)
ms:contentKeyID: 49709977
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmCourseTypeNotes Upgrade Script [AX 2012]


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
<td><p>updateHcmCourseTypeNotes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmCourseTypeNotes table from the DEL_HRMCourseNotes table.</p></td>
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
<td><p>DEL_HRMCourseNotes</p></td>
</tr>
<tr class="even">
<td><p>HcmCourseType</p></td>
</tr>
<tr class="odd">
<td><p>HcmCourseTypeNotes</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The CourseType field in the HcmCourseTypeNotes table is the foreign key to the HcmCourseType table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMCourseNotes</p></th>
<th><p>To Table: HcmCourseTypeNotes</p></th>
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
<td><p>HcmCourseTypeNotes</p></td>
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
<td><p>DEL_HRMCourseNotes</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

