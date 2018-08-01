﻿---
title: ReleaseUpdateTransformDB40_Ledger.setBudgetTransactionLineFields Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.setBudgetTransactionLineFields Upgrade Script
ms:assetid: 77951605-bc76-56e6-b32e-9c25d7021d2a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719375(v=AX.60)
ms:contentKeyID: 49709166
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.setBudgetTransactionLineFields Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>setBudgetTransactionLineFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the field values for the specified BudgetTransactionLine record based on the specified LedgerBudget record.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>BudgetTransactionLine</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerBudget</p></th>
<th><p>To Table: BudgetTransactionLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>StartDate</p></td>
<td><p>Date</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>TransactionCurrency</p></td>
</tr>
<tr class="odd">
<td><p>Qty</p></td>
<td><p>Quantity</p></td>
</tr>
<tr class="even">
<td><p>Price</p></td>
<td><p>Price</p></td>
</tr>
<tr class="odd">
<td><p>Amount</p></td>
<td><p>TransactionCurrencyAmount</p></td>
</tr>
<tr class="even">
<td><p>Cov</p></td>
<td><p>IncludeInCashFlowForecast</p></td>
</tr>
<tr class="odd">
<td><p>TaxGroup</p></td>
<td><p>TaxGroup</p></td>
</tr>
<tr class="even">
<td><p>Comment</p></td>
<td><p>Comment</p></td>
</tr>
<tr class="odd">
<td><p>ProjTransId</p></td>
<td><p>ProjTransBudgetTransId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

