---
title: ReleaseUpdateDB60_Payroll.updatePayrollPayStatementEarningLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollPayStatementEarningLine Upgrade Script
ms:assetid: d23f2a0c-88a5-1e47-9943-a74b6c59f34a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686974(v=AX.60)
ms:contentKeyID: 49711424
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollPayStatementEarningLine Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Payroll</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePayrollPayStatementEarningLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollPayStatementEarningLine table from the PrlEmployeePayElementsTrans table.</p></td>
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
<td><p>PayrollPayStatementEarningLine</p></td>
</tr>
<tr class="even">
<td><p>PayrollTaxRegion</p></td>
</tr>
<tr class="odd">
<td><p>PayrollTaxRegionForSymmetry</p></td>
</tr>
<tr class="even">
<td><p>PayrollWorkerTaxRegion</p></td>
</tr>
<tr class="odd">
<td><p>PRLEmployeePayElementsTransPosted</p></td>
</tr>
<tr class="even">
<td><p>PRLEmployeePayElementsTrans</p></td>
</tr>
<tr class="odd">
<td><p>PrlPayElements</p></td>
</tr>
<tr class="even">
<td><p>PrlGeneralLiabilityInsurance</p></td>
</tr>
<tr class="odd">
<td><p>DEL_PRLWorkerCompensation</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will create records in the PayrollPayStatementEarningLine table from the PrlEmployeePayElementsTrans table records of the type earnings.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLEmployeePayElementsTransPosted</p></th>
<th><p>To Table: PayrollPayStatementEarningLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayElementDate</p></td>
<td><p>AccountingDate</p></td>
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
<th><p>From Table: PRLEmployeePayElementsTrans</p></th>
<th><p>To Table: PayrollPayStatementEarningLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amount</p></td>
<td><p>AccountingCurrencyAmount</p></td>
</tr>
<tr class="even">
<td><p>PaymentLineModified</p></td>
<td><p>IsPayStatementLineOverridden</p></td>
</tr>
<tr class="odd">
<td><p>NormalHours</p></td>
<td><p>Quantity</p></td>
</tr>
<tr class="even">
<td><p>HourlyRate</p></td>
<td><p>EarningRate</p></td>
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
<th><p>From Table: PayrollWorkerTaxRegion</p></th>
<th><p>To Table: PayrollPayStatementEarningLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>WorkerTaxRegion</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

