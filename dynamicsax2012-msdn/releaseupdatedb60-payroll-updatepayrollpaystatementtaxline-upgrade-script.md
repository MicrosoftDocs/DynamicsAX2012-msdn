---
title: ReleaseUpdateDB60_Payroll.updatePayrollPayStatementTaxLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollPayStatementTaxLine Upgrade Script
ms:assetid: 64e7af73-1d36-079a-f785-2b89b5991c93
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719179(v=AX.60)
ms:contentKeyID: 49708717
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollPayStatementTaxLine Upgrade Script 


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
<td><p>updatePayrollPayStatementTaxLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollPayStatementTaxLine table from the PrlEmployeePayElementsTrans table.</p></td>
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
<td><p>PayrollPayStatementTaxLine</p></td>
</tr>
<tr class="even">
<td><p>PRLEmployeePayElementsTransPosted</p></td>
</tr>
<tr class="odd">
<td><p>PRLEmployeePayElementsTrans</p></td>
</tr>
<tr class="even">
<td><p>PrlUSTaxTransactionHistory</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will create records in the PayrollPayStatementTaxLine table from the PrlEmployeePayElementsTrans table records of the type withholding tax employer tax.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLEmployeePayElementsTransPosted</p></th>
<th><p>To Table: PayrollPayStatementTaxLine</p></th>
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
<th><p>To Table: PayrollPayStatementTaxLine</p></th>
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
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PrlUSTaxTransactionHistory</p></th>
<th><p>To Table: PayrollPayStatementTaxLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TaxCode</p></td>
<td><p>TaxCode</p></td>
</tr>
</tbody>
</table>

  


