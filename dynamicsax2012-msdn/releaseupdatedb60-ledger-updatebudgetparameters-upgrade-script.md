---
title: ReleaseUpdateDB60_Ledger.updateBudgetParameters Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateBudgetParameters Upgrade Script
ms:assetid: 8be3da7c-50e6-033a-aea1-ec0136347d02
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736441(v=AX.60)
ms:contentKeyID: 49709630
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateBudgetParameters Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBudgetParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the BudgetParameters table by setting the value CashFlowForecastPeriodAllocationKey field to that of the removed BudgetSettle value from the LedgerParameters table.</p></td>
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
<td><p>BudgetParameters</p></td>
</tr>
<tr class="even">
<td><p>LedgerParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

The BudgetCheck and BudgetSettle fields of the LedgerParameters table will be removed. The CashFlowForecastPeriodAllocationKey field is added to the BudgetParameters table and is set to the old value of the LedgerParameters.BudgetSettle field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerParameters</p></th>
<th><p>To Table: BudgetParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BudgetSettle</p></td>
<td><p>CashFlowForecastPeriodAllocationKey</p></td>
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
<td><p>BudgetParameters</p></td>
<td><p>CashFlowForecastPeriodAllocationKey</p></td>
<td><p>LedgerAllocateKeyId</p></td>
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
<td><p>LedgerParameters</p></td>
<td><p>BudgetCheck</p></td>
</tr>
<tr class="even">
<td><p>LedgerParameters</p></td>
<td><p>BudgetSettle</p></td>
</tr>
</tbody>
</table>

  


