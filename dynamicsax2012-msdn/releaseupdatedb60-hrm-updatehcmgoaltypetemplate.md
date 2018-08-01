---
title: ReleaseUpdateDB60_HRM.updateHcmGoalTypeTemplate
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmGoalTypeTemplate
ms:assetid: fe3ae926-b584-15c2-b2ae-c72eaa129a79
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720188(v=AX.60)
ms:contentKeyID: 49712493
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmGoalTypeTemplate 


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
<td><p>updateHcmGoalTypeTemplate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmGoalTypeTemplate&lt;/c&gt; table from the &lt;c&gt;HRMGoalTypeTemplate&lt;/c&gt; table.</p></td>
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
<td><p>HcmGoalType</p></td>
</tr>
<tr class="even">
<td><p>HcmGoalTypeTemplate</p></td>
</tr>
<tr class="odd">
<td><p>HRMGoalTypeTemplate</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The \<c\>GoalType\</c\> field in the \<c\>HcmGoalTypeTemplate\</c\> table is the foreign key to the \<c\>HcmGoalType\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMGoalTypeTemplate</p></th>
<th><p>To Table: HcmGoalTypeTemplate</p></th>
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
<td><p>HcmGoalTypeTemplate</p></td>
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
<td><p>HRMGoalTypeTemplate</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


