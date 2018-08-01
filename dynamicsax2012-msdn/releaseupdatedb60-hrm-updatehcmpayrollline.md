---
title: ReleaseUpdateDB60_HRM.updateHcmPayrollLine
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPayrollLine
ms:assetid: c4a69ba3-a068-49d1-bfa3-62d333f9a5d2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719504(v=AX.60)
ms:contentKeyID: 49711071
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPayrollLine 


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
<td><p>updateHcmPayrollLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmPayrollLine&lt;/c&gt; table from the &lt;c&gt;HRMPayrollLine&lt;/c&gt; table.</p></td>
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
<td><p>HcmPayrollLine</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
</tr>
<tr class="odd">
<td><p>HCMWorkerAffiliation</p></td>
</tr>
<tr class="even">
<td><p>HRMPayrollLine</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The \<c\>EmployeeAffiliation\</c\> field in the \<c\>HcmPayrollLine\</c\> table is the foreign key to the \<c\>HcmEmployeeAffiliation\</c\> table. The \<c\>PayrollCategory\</c\> field in the \<c\>HcmPayrollLine\</c\> table is the foreign key to the \<c\>HcmPayrollCategory\</c\> table. The \<c\>PayrollPremium\</c\> field in the \<c\>HcmPayrollLine\</c\> table is the foreign key to the \<c\>HcmPayrollPremium\</c\> table. The \<c\>ReasonCode\</c\> field in the \<c\>HcmPayrollLine\</c\> table is the foreign key to the \<c\>HcmReasonCode\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMPayrollLine</p></th>
<th><p>To Table: HcmPayrollLine</p></th>
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
<td><p>HcmPayrollLine</p></td>
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
<td><p>HRMPayrollLine</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


