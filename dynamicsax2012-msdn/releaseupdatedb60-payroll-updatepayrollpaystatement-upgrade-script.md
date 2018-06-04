---
title: ReleaseUpdateDB60_Payroll.updatePayrollPayStatement Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollPayStatement Upgrade Script
ms:assetid: deba8134-1024-fe9e-8aee-72f0a54689a8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737263(v=AX.60)
ms:contentKeyID: 49711705
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollPayStatement Upgrade Script 


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
<td><p>updatePayrollPayStatement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollPayStatement table from the PrlEmployeePayElementsTransPosted table.</p></td>
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
<td><p>PayrollPayStatement</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will create records in the PayrollPayStatement table from the PrlEmployeePayElementsTransPosted table records that are posted and paid. Creates required document numbers based on the number sequence.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLEmployeePayElementsTransPosted</p></th>
<th><p>To Table: PayrollPayStatement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Worker</p></td>
<td><p>Worker</p></td>
</tr>
<tr class="even">
<td><p>PaymMode</p></td>
<td><p>PaymentMethodType</p></td>
</tr>
<tr class="odd">
<td><p>VoidPost</p></td>
<td><p>IsReversed</p></td>
</tr>
<tr class="even">
<td><p>PaymentDate</p></td>
<td><p>PaymentDate</p></td>
</tr>
<tr class="odd">
<td><p>RunType</p></td>
<td><p>PaymentType</p></td>
</tr>
<tr class="even">
<td><p>SalaryExpenseJournalId</p></td>
<td><p>PaymentJournalBatchNum</p></td>
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
<th><p>To Table: PayrollPayStatement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amount</p></td>
<td><p>GrossAccountingCurrencyAmount</p></td>
</tr>
<tr class="even">
<td><p>Amount</p></td>
<td><p>NetAccountingCurrencyAmount</p></td>
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
<th><p>From Table: DEL_PRLPayrollPeriod</p></th>
<th><p>To Table: PayrollPayStatement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>PayPeriod</p></td>
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
<th><p>From Table: PRLEmployeePayElementsTransPosted</p></th>
<th><p>To Table: DocuRef</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>txt</p></td>
<td><p>Notes</p></td>
</tr>
<tr class="even">
<td><p>PayElementDate</p></td>
<td><p>createdDateTime</p></td>
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
<th><p>To Table: DocuRef</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>RefCompanyId</p></td>
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
<th><p>From Table: PayrollPayStatement</p></th>
<th><p>To Table: DocuRef</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>TableId</p></td>
<td><p>RefTableId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

