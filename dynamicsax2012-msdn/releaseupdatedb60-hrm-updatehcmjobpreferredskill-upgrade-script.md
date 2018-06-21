﻿---
title: ReleaseUpdateDB60_HRM.updateHcmJobPreferredSkill Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmJobPreferredSkill Upgrade Script
ms:assetid: 9e7186e5-f3c3-feb4-de18-b3df441bcdfc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736645(v=AX.60)
ms:contentKeyID: 49710087
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmJobPreferredSkill Upgrade Script [AX 2012]


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
<td><p>updateHcmJobPreferredSkill</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts data into the HcmJobPreferredSkill table from the HRMJobSkillProfile table.</p></td>
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
<td><p>HcmJobPreferredSkill</p></td>
</tr>
<tr class="even">
<td><p>HRMJobSkillProfile</p></td>
</tr>
<tr class="odd">
<td><p>HcmJob</p></td>
</tr>
<tr class="even">
<td><p>HcmSkill</p></td>
</tr>
<tr class="odd">
<td><p>HcmRatingLevel</p></td>
</tr>
</tbody>
</table>


## Remarks

1.  The Job field which holds record ID from HcmJob table replaces the Reference field.

2.  The Skill field which holds record ID from the HcmSkill table replaces the SkillId field.

3.  The RatingLevel field which holds record ID from the HcmRatingLevel table replaces the RatingLevelId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMJobSkillProfile</p></th>
<th><p>To Table: HcmJobPreferredSkill</p></th>
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
<td><p>HcmJobPreferredSkill</p></td>
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
<td><p>HRMJobSkillProfile</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

