---
title: ReleaseUpdateDB60_HRM.updateHcmGoalActivity
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmGoalActivity
ms:assetid: 7849ec3e-54b3-8fc1-2c4a-962d89459903
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719382(v=AX.60)
ms:contentKeyID: 49709173
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmGoalActivity [AX 2012]


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
<td><p>updateHcmGoalActivity</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmGoalActivity&lt;/c&gt; table from the &lt;c&gt;HRMGoalActivity&lt;/c&gt; table.</p></td>
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
<td><p>HcmGoalActivity</p></td>
</tr>
<tr class="even">
<td><p>HRMGoal</p></td>
</tr>
<tr class="odd">
<td><p>HRMGoalActivity</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending the \<c\>DataAreaId\</c\> field to the \<c\>ActivityId\</c\> field of the \<c\>HRMGoalActivity\</c\> table to create new, unique identifiers for the \<c\>HcmGoalActivity\</c\> table when multiple companies exist. If only one company exists, the \<c\>DataAreaId\</c\> field will not be appended. The \<c\>Goal\</c\> field in the \<c\>HcmGoalActivity\</c\> table is the foreign key to the \<c\>HcmGoal\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMGoalActivity</p></th>
<th><p>To Table: HcmGoalActivity</p></th>
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
<td><p>HcmGoalActivity</p></td>
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
<td><p>HRMGoalActivity</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

