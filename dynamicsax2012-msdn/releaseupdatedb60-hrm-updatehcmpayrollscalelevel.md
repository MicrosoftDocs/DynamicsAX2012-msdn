---
title: ReleaseUpdateDB60_HRM.updateHcmPayrollScaleLevel
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPayrollScaleLevel
ms:assetid: 991843a1-e571-2e2b-51fd-f4f25c178b82
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686260(v=AX.60)
ms:contentKeyID: 49709963
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPayrollScaleLevel 


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
<td><p>updateHcmPayrollScaleLevel</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmPayrollScaleLevel&lt;/c&gt; table from the &lt;c&gt;HRMPayrollScaleLevel&lt;/c&gt; table.</p></td>
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
<td><p>HcmPayrollFrame</p></td>
</tr>
<tr class="even">
<td><p>HcmPayrollScaleLevel</p></td>
</tr>
<tr class="odd">
<td><p>HRMEmplCategory</p></td>
</tr>
<tr class="even">
<td><p>HRMPayrollScaleLevel</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The \<c\>PayrollFrame\</c\> field in the \<c\>HcmPayrollScaleLevel\</c\> table is the foreign key to the \<c\>HcmPayrollFrame\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMPayrollScaleLevel</p></th>
<th><p>To Table: HcmPayrollScaleLevel</p></th>
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
<td><p>HcmPayrollScaleLevel</p></td>
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
<td><p>HRMPayrollScaleLevel</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


