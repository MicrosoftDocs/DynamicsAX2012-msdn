---
title: ReleaseUpdateDB63_PayrollMinor .updateAccrualBasisEarningCode Upgrade Script
TOCTitle: ReleaseUpdateDB63_PayrollMinor .updateAccrualBasisEarningCode Upgrade Script
ms:assetid: 3c670f33-d414-c469-843d-8246ceb047dd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702717(v=AX.60)
ms:contentKeyID: 65236173
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB63\_PayrollMinor .updateAccrualBasisEarningCode Upgrade Script 


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB63_PayrollMinor</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateAccrualBasisEarningCode</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the data in &lt;c&gt;PayrollAccrualBasisEarningcode&lt;/c&gt; table.</p></td>
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
<td><p>Payroll</p></td>
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
<td><p>PAYROLLACCRUALBASISEARNINGCODE</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLEARNINGCODE</p></td>
</tr>
<tr class="odd">
<td><p>PAYROLLACCRUALEARNINGCODE</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLACCRUAL</p></td>
</tr>
</tbody>
</table>


## Remarks

Inserts records into the PayrollAccrualBasisEarningCode table from the PayrollEarningCode table on the basis of IsIncludedInAccrual field in the PayrollAccrual table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PayrollEarningCode</p></th>
<th><p>To Table: PayrollAccrualBasisEarningCode</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>EarningCode</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PayrollAccrual</p></th>
<th><p>To Table: PayrollAccrualBasisEarningCode</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Accrual</p></td>
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
<td><p>PayrollAccrualBasisEarningCode</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PayrollAccrual</p></td>
<td><p>AccrualMethod</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PayrollAccrual</p></td>
<td><p>CustomAccrualDate</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PayrollAccrual</p></td>
<td><p>Frequency</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PayrollAccrual</p></td>
<td><p>WorkerAccrualDateMethod</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PayrollWorkerEnrolledAccrual</p></td>
<td><p>AccrualDateBasis</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PayrollWorkerEnrolledAccrual</p></td>
<td><p>CustomAccuralDate</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


