﻿---
title: ReleaseUpdateDB60_HRM.updateHcmUnions
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmUnions
ms:assetid: 6769e831-dafd-8bd4-2304-533237601a6a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719246(v=AX.60)
ms:contentKeyID: 49708784
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmUnions 


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
<td><p>updateHcmUnions</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmUnions&lt;/c&gt; table from the &lt;c&gt;HRMUnions&lt;/c&gt; table.</p></td>
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
<td><p>HcmUnions</p></td>
</tr>
<tr class="even">
<td><p>HRMUnions</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will discard duplicate records if the \<c\>HrmUnionsId\</c\> field and the \<c\>Description\</c\> field of the \<c\>HRMUnions\</c\> table are identical. The new unique identifier \<c\>UnionsId\</c\> field of the \<c\>HcmUnions\</c\> table combines the \<c\>HrmUnionsId\</c\> field and the \<c\>DataAreaId\</c\> field of the \<c\>HRMUnions\</c\> table from the first record found. All records found that are identified as duplicates in other companies will be discarded. If only one company exists, the \<c\>DataAreaId\</c\> field will not be appended.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMUnions</p></th>
<th><p>To Table: HcmUnions</p></th>
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
<td><p>HcmUnions</p></td>
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
<td><p>HRMUnions</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


