---
title: ReleaseUpdateDB60_HRM.updateHcmCourseTypeSkillProfile Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmCourseTypeSkillProfile Upgrade Script
ms:assetid: 6a9e72e9-bd97-fb43-bd1f-158a4b651696
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685677(v=AX.60)
ms:contentKeyID: 49708878
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmCourseTypeSkillProfile Upgrade Script 


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
<td><p>updateHcmCourseTypeSkillProfile</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmCourseTypeSkillProfile table from the HRMCourseTypeSkillProfile table.</p></td>
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
<td><p>HcmCourseTypeSkillProfile</p></td>
</tr>
<tr class="odd">
<td><p>HcmRatingLevel</p></td>
</tr>
<tr class="even">
<td><p>HcmRatingModel</p></td>
</tr>
<tr class="odd">
<td><p>HcmSkill</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The CourseType field in the HcmCourseTypeSkillProfile table is the foreign key to the HcmCourseType table. The Skill field in the HcmCourseTypeSkillProfile table is the foreign key to the HcmSkill table. The RatingLevel field in the HcmCourseTypeSkillProfile table is the foreign key to the HcmRatingLevel table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMCourseTypeSkillProfile</p></th>
<th><p>To Table: HcmCourseTypeSkillProfile</p></th>
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
<td><p>HcmCourseTypeSkillProfile</p></td>
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
<td><p>HRMCourseTypeSkillProfile</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


