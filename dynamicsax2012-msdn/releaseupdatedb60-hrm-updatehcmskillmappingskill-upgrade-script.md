﻿---
title: ReleaseUpdateDB60_HRM.updateHcmSkillMappingSkill Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmSkillMappingSkill Upgrade Script
ms:assetid: eccf52c2-bfb4-b0aa-5ea7-7dfee9b91ce2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719925(v=AX.60)
ms:contentKeyID: 49711997
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmSkillMappingSkill Upgrade Script [AX 2012]


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
<td><p>updateHcmSkillMappingSkill</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmSkillMappingSkill table from the HRMSkillMappingSkill table.</p></td>
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
<td><p>HcmRatingLevel</p></td>
</tr>
<tr class="even">
<td><p>HcmRatingModel</p></td>
</tr>
<tr class="odd">
<td><p>HcmSkill</p></td>
</tr>
<tr class="even">
<td><p>HcmSkillMappingHeader</p></td>
</tr>
<tr class="odd">
<td><p>HcmSkillMappingSkill</p></td>
</tr>
<tr class="even">
<td><p>HRMSkillMappingSkill</p></td>
</tr>
</tbody>
</table>


## Remarks

The SkillMappingHeader field holding the RecId value from the HcmSkillMappingTable table replaces the hrmSkillMappingTableId field. The SKill field holding the RecId value from the HcmSkill table replaces the hrmSkillId field. The RatingLevel field holding the RecId value from the HcmRatingLevel table replaces the ratingLevel field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMSkillMappingSkill</p></th>
<th><p>To Table: HcmSkillMappingSkill</p></th>
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
<td><p>HcmSkillMappingSkill</p></td>
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
<td><p>HRMSkillMappingSkill</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

