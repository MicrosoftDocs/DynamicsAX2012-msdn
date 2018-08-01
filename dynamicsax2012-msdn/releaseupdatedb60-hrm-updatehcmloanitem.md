---
title: ReleaseUpdateDB60_HRM.updateHcmLoanItem
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmLoanItem
ms:assetid: c160d27a-3914-167d-3c49-80fab175b5fb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686803(v=AX.60)
ms:contentKeyID: 49711000
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmLoanItem 


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
<td><p>updateHcmLoanItem</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmLoanItem&lt;/c&gt; table from the &lt;c&gt;HRMLoanTable&lt;/c&gt; table.</p></td>
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
<td><p>EmplTable</p></td>
</tr>
<tr class="even">
<td><p>HcmLoanItem</p></td>
</tr>
<tr class="odd">
<td><p>HcmWorker</p></td>
</tr>
<tr class="even">
<td><p>HRMLoanTable</p></td>
</tr>
<tr class="odd">
<td><p>HRMLoanType</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending the \<c\>DataAreaId\</c\> field to the \<c\>HrmLoanId\</c\> field of the \<c\>HRMLoanTable\</c\> table to create new, unique identifiers for the \<c\>HcmLoanItem\</c\> table when multiple companies exist. If only one company exists, the \<c\>DataAreaId\</c\> field will not be appended. The \<c\>Worker\</c\> field in the \<c\>HcmLoanItem\</c\> table is the foreign key to the \<c\>HcmWorker\</c\> table. The \<c\>LoanType\</c\> field in the \<c\>HcmLoanItem\</c\> table is the foreign key to the \<c\>HcmLoanType\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMLoanTable</p></th>
<th><p>To Table: HcmLoanItem</p></th>
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
<td><p>HcmLoanItem</p></td>
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
<td><p>HRMLoanTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


