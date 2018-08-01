---
title: ReleaseUpdateDB60_Payroll.updatePayrollPayStatementBenefitLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollPayStatementBenefitLine Upgrade Script
ms:assetid: e011e934-40a2-0e9f-0346-3bfcaab1babd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737265(v=AX.60)
ms:contentKeyID: 49711707
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollPayStatementBenefitLine Upgrade Script 


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
<td><p>updatePayrollPayStatementBenefitLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollPayStatementBenefitLine table from the PrlEmployeePayElementsTrans table.</p></td>
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
<td><p>PayrollPayStatementBenefitLine</p></td>
</tr>
<tr class="even">
<td><p>PRLEmployeePayElementsTransPosted</p></td>
</tr>
<tr class="odd">
<td><p>HcmBenefitType</p></td>
</tr>
<tr class="even">
<td><p>HcmBenefitOption</p></td>
</tr>
<tr class="odd">
<td><p>HcmBenefitPlan</p></td>
</tr>
<tr class="even">
<td><p>HcmBenefit</p></td>
</tr>
<tr class="odd">
<td><p>PRLEmployeePayElementsTrans</p></td>
</tr>
<tr class="even">
<td><p>PRLDeductionCodeTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will create records in the PayrollPayStatementBenefitLine table from the PrlEmployeePayElementsTrans table records of the type deduction, contribution, worker's compensation, GLI and fringe.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLEmployeePayElementsTransPosted</p></th>
<th><p>To Table: PayrollPayStatementBenefitLine</p></th>
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
<th><p>To Table: PayrollPayStatementBenefitLine</p></th>
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
<th><p>From Table: HcmBenefit</p></th>
<th><p>To Table: PayrollPayStatementBenefitLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Benefit</p></td>
</tr>
</tbody>
</table>

  


