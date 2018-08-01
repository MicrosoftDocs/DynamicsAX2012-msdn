---
title: ReleaseUpdateDB60_HRM.updateHcmGoalHeading Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmGoalHeading Upgrade Script
ms:assetid: bf918d42-8631-8bd2-a1f1-fbfa769c5e35
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686743(v=AX.60)
ms:contentKeyID: 49710942
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmGoalHeading Upgrade Script 


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
<td><p>updateHcmGoalHeading</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmGoalHeading table from the HRMGoalHeading table.</p></td>
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
<td><p>HcmGoalHeading</p></td>
</tr>
<tr class="even">
<td><p>HRMGoalHeading</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will discard duplicate records if the HeadingId field and the Description field of the HRMGoalHeading table are identical. The new unique identifier GoalHeadingId field of the HcmGoalHeading table combines the HeadingId field and the DataAreaId field of the HRMGoalHeading table from the first record found. All records found that are identified as duplicates in other companies will be discarded. If only one company exists, the DataAreaId field will not be appended.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMGoalHeading</p></th>
<th><p>To Table: HcmGoalHeading</p></th>
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
<td><p>HcmGoalHeading</p></td>
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
<td><p>HRMGoalHeading</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


