---
title: ReleaseUpdateDB60_HRM.updateHcmRatingModel
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmRatingModel
ms:assetid: 6735659d-6844-564c-18c9-c364cb0046ea
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719239(v=AX.60)
ms:contentKeyID: 49708777
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmRatingModel 


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
<td><p>updateHcmRatingModel</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmRatingModel&lt;/c&gt; table from the &lt;c&gt;HRMRatingModel&lt;/c&gt; table.</p></td>
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
<td><p>HcmRatingModel</p></td>
</tr>
<tr class="even">
<td><p>HRMRatingModel</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending the \<c\>DataAreaId\</c\> to the \<c\>RatingModelId\</c\> field of the \<c\>HRMRatingModel\</c\> table to create new, unique identifiers for the \<c\>HcmRatingModel\</c\> table when multiple companies exist. If only one company exists, the \<c\>DataAreaId\</c\> field will not be appended.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMRatingModel</p></th>
<th><p>To Table: HcmRatingModel</p></th>
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
<td><p>HcmRatingModel</p></td>
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
<td><p>HRMRatingModel</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


