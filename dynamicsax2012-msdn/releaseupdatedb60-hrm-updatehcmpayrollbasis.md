---
title: ReleaseUpdateDB60_HRM.updateHcmPayrollBasis
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPayrollBasis
ms:assetid: b6050995-6c68-3a46-714f-20f5c847a74c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737020(v=AX.60)
ms:contentKeyID: 49710701
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPayrollBasis 


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
<td><p>updateHcmPayrollBasis</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmPayrollBasis&lt;/c&gt; table from the &lt;c&gt;HRMPayrollBasis&lt;/c&gt; table.</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
</tr>
<tr class="odd">
<td><p>HcmPayrollBasis</p></td>
</tr>
<tr class="even">
<td><p>HcmPayrollFrame</p></td>
</tr>
<tr class="odd">
<td><p>HcmPayrollFrameCategory</p></td>
</tr>
<tr class="even">
<td><p>HcmPayrollScaleLevel</p></td>
</tr>
<tr class="odd">
<td><p>HcmWorker</p></td>
</tr>
<tr class="even">
<td><p>HCMWorkerAffiliation</p></td>
</tr>
<tr class="odd">
<td><p>HRMPayrollBasis</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The \<c\>PayrollScaleLevel\</c\> field in the \<c\>HcmPayrollBasis\</c\> table is the foreign key to the \<c\>HcmPayrollScaleLevel\</c\> table. The \<c\>EmployeeAffiliation\</c\> field in the \<c\>HcmPayrollBasis\</c\> table is the foreign key to the \<c\>HcmEmployeeAffiliation\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMPayrollBasis</p></th>
<th><p>To Table: HcmPayrollBasis</p></th>
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
<td><p>HcmPayrollBasis</p></td>
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
<td><p>HRMPayrollBasis</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


