---
title: ReleaseUpdateDB60_HRM.updateHcmPersonLoan Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPersonLoan Upgrade Script
ms:assetid: c07ff56b-11d8-b28f-264e-70dd445e2804
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686767(v=AX.60)
ms:contentKeyID: 49710964
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPersonLoan Upgrade Script 


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
<td><p>updateHcmPersonLoan</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmPersonLoan table from the HRMVirtualNetworkLoan table.</p></td>
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
<td><p>ContactPerson</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
</tr>
<tr class="odd">
<td><p>HcmLoanItem</p></td>
</tr>
<tr class="even">
<td><p>HcmPersonLoan</p></td>
</tr>
<tr class="odd">
<td><p>HRMApplicantTable</p></td>
</tr>
<tr class="even">
<td><p>HRMVirtualNetworkLoan</p></td>
</tr>
<tr class="odd">
<td><p>HRMVirtualNetworkTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The Person field, which has the RecId value from the DirPerson table, replaces the HrmVirtualNetworkId field. The Loan field, which has the RecId value from the HcmLoan table, replaces the HrmLoanId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMVirtualNetworkLoan</p></th>
<th><p>To Table: HcmPersonLoan</p></th>
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
<td><p>HcmPersonLoan</p></td>
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
<td><p>HRMVirtualNetworkLoan</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


