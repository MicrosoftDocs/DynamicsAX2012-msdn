---
title: ReleaseUpdateTransformDB50_Ledger.currencyLedgerAccountDeltaPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.currencyLedgerAccountDeltaPreProcessing Upgrade Script
ms:assetid: d424d397-29e1-e4ea-27f6-b7d55c3c4c8a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687013(v=AX.60)
ms:contentKeyID: 49711461
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.currencyLedgerAccountDeltaPreProcessing Upgrade Script 


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
<td><p>currencyLedgerAccountDeltaPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates account number data from the Currency table to the CurrencyLedgerGainLossAccount table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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
<td><p>Currency</p></td>
</tr>
</tbody>
</table>


## Remarks

One record is created in the CurrencyLedgerGainLossAccount table for each account in the Currency table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: Currency</p></th>
<th><p>To Table: CurrencyLedgerGainLossAccount</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CurrencyCode</p></td>
<td><p>CurrencyCode</p></td>
</tr>
<tr class="even">
<td><p>LedgerAccountLoss</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>LedgerAccountNonrealLoss</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>LedgerAccountNonrealProfit</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>LedgerAccountProfit</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Ledger</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>AccountType</p></td>
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
<th><p>From Table:</p></th>
<th><p>To Table:</p></th>
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
<td><p>CurrencyLedgerGainLossAccount</p></td>
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
<td><p>Currency</p></td>
<td><p>LedgerAccountLoss</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>LedgerAccountNonrealLoss</p></td>
</tr>
<tr class="odd">
<td><p>Currency</p></td>
<td><p>LedgerAccountNonrealProfit</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>LedgerAccountProfit</p></td>
</tr>
</tbody>
</table>

  


