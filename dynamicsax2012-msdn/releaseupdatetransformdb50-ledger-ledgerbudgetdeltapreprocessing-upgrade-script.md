---
title: ReleaseUpdateTransformDB50_Ledger.ledgerBudgetDeltaPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.ledgerBudgetDeltaPreProcessing Upgrade Script
ms:assetid: 5770f517-60a3-b5a5-031e-4210b6f34e27
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736210(v=AX.60)
ms:contentKeyID: 49708385
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.ledgerBudgetDeltaPreProcessing Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerBudgetDeltaPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the LedgerBudget table to the BudgetTransactionHeader and BudgetTransactionLine tables.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p>
<p>Preprocessing 60: Single user</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>LedgerBudget</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade inserts records into the BudgetTransactionHeader and BudgetTransactionLine tables from the LedgerBudget table, updates existing records in the BudgetTransactionHeader and BudgetTransactionLine tables, and deletes records from the BudgetTransactionHeader and BudgetTransactionLine tables that no longer have an associated record from the LedgerBudget table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerBudget</p></th>
<th><p>To Table: BudgetTransactionHeader</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>TransactionNumber</p></td>
</tr>
<tr class="even">
<td><p>ModelNum</p></td>
<td><p>BudgetModelId</p></td>
</tr>
<tr class="odd">
<td><p>StartDate</p></td>
<td><p>Date</p></td>
</tr>
<tr class="even">
<td><p>Active</p></td>
<td><p>TransactionStatus</p></td>
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
<td><p>AmountMST</p></td>
<td><p>AccountingCurrencyAmount</p></td>
</tr>
<tr class="odd">
<td><p>Cov</p></td>
<td><p>IncludeInCashFlowForecast</p></td>
</tr>
<tr class="even">
<td><p>TaxGroup</p></td>
<td><p>TaxGroup</p></td>
</tr>
<tr class="odd">
<td><p>Comment</p></td>
<td><p>Comment</p></td>
</tr>
<tr class="even">
<td><p>ProjTransId</p></td>
<td><p>ProjTransBudgetTransId</p></td>
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
<td><p>BudgetTransactionHeader</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>BudgetTransactionLine</p></td>
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
<td><p>LedgerBudget</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


