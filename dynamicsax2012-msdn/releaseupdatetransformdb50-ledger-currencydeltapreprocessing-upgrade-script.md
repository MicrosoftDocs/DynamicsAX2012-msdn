---
title: ReleaseUpdateTransformDB50_Ledger.currencyDeltaPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.currencyDeltaPreProcessing Upgrade Script
ms:assetid: cf8b39ca-623a-a9b9-b6e0-897782c28561
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686906(v=AX.60)
ms:contentKeyID: 49711356
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.currencyDeltaPreProcessing Upgrade Script 


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
<td><p>currencyDeltaPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Currency table to be a shared table.</p></td>
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

This script will populate the Shadow\_Currency table with the currencies that are selected in the prepare currencies for upgrade task. This scripts needs to be run after the prepare currencies for upgrade task. The prepare currencies for upgrade task will populate the CurrencyUpgradeParameters, CurrencyUpgradeSelection, and CurrencyUpgradeGlobal tables.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: Currency</p></th>
<th><p>To Table: CurrencyOnlineConversion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CurrencyCode</p></td>
<td><p>CurrencyCode</p></td>
</tr>
<tr class="even">
<td><p>CurrencyPrefix</p></td>
<td><p>Name</p></td>
</tr>
<tr class="odd">
<td><p>CurrencySuffix</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Affix</p></td>
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
<td><p>CurrencyEuroDenomination</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>CurrencyOnlineConversion</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
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
<td><p>RoundOffAmountType</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>RoundOffProject</p></td>
</tr>
<tr class="odd">
<td><p>Currency</p></td>
<td><p>RoundOffTypeProject</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>OnLineConversionTool</p></td>
</tr>
<tr class="odd">
<td><p>Currency</p></td>
<td><p>CurrencyPrefix</p></td>
</tr>
<tr class="even">
<td><p>Currency</p></td>
<td><p>CurrencySuffix</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

