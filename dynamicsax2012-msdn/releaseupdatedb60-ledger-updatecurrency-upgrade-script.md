---
title: ReleaseUpdateDB60_Ledger.updateCurrency Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateCurrency Upgrade Script
ms:assetid: 89ae57c1-21a5-bbd0-beb6-65fedb1311cc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736392(v=AX.60)
ms:contentKeyID: 49709582
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateCurrency Upgrade Script 


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
<td><p>updateCurrency</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates additional records in the Currency table and the ISOCurrencyCode table.</p></td>
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
<tr class="even">
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
<tr class="even">
<td><p>ISOCurrencyCode</p></td>
</tr>
</tbody>
</table>


## Remarks

Creates additional records in the Currency table so that there will be a record for every International Standards Operation (ISO) currency code. Creates an unknown record in the ISOCurrencyCode table.

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
<td><p>Currency</p></td>
<td><p>IsEuro</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>RoundingPrecision</p></td>
<td><p>RoundOff</p></td>
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
<tr class="odd">
<td><p>Currency</p></td>
<td><p>RoundOffProject</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>RoundOffTypeProject</p></td>
</tr>
<tr class="odd">
<td><p>Currency</p></td>
<td><p>CurrencyPrefix</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>CurrencySuffix</p></td>
</tr>
<tr class="odd">
<td><p>Currency</p></td>
<td><p>OnLineConversionTool</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>RoundOffAmountType</p></td>
</tr>
</tbody>
</table>

  


