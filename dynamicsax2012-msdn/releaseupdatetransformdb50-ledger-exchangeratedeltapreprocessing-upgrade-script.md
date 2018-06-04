---
title: ReleaseUpdateTransformDB50_Ledger.exchangeRateDeltaPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.exchangeRateDeltaPreProcessing Upgrade Script
ms:assetid: f1b8a0e5-c588-e021-769a-c97b4c96f003
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737435(v=AX.60)
ms:contentKeyID: 49712130
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.exchangeRateDeltaPreProcessing Upgrade Script 


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
<td><p>exchangeRateDeltaPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms the ExchRates table to the ExchangeRateType, ExchangeRateCurrencyPair, and ExchangeRate tables.</p></td>
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
<td><p>ExchRates</p></td>
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
<th><p>From Table: ExchRates</p></th>
<th><p>To Table: ExchangeRateCurrencyPair</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CurrencyCode</p></td>
<td><p>FromCurrencyCode</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>ToCurrencyCode</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>ExchangeRateType</p></td>
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
<th><p>From Table: LedgerParameters</p></th>
<th><p>To Table: ExchangeRateCurrencyPair</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExpressExchRate</p></td>
<td><p>ExchangeRateDisplayFactor</p></td>
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
<th><p>From Table: ExchRates</p></th>
<th><p>To Table: ExchangeRate</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchRate</p></td>
<td><p>ExchangeRate</p></td>
</tr>
<tr class="even">
<td><p>FromDate</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>ValidTo</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>ExchangeRateCurrencyPair</p></td>
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
<td><p>ExchangeRateType</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>ExchangeRateCurrencyPair</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>ExchangeRate</p></td>
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
<td><p>ExchRates</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

