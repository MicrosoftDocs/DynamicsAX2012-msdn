---
title: ReleaseUpdateDB60_Ledger.updateTaxYearlyComSetupExclued_IT Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxYearlyComSetupExclued_IT Upgrade Script
ms:assetid: 0a939106-1c87-9c3e-cf3e-c1267af82eff
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735623(v=AX.60)
ms:contentKeyID: 49706534
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxYearlyComSetupExclued\_IT Upgrade Script 


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
<td><p>updateTaxYearlyComSetupExclued_IT</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The fromAccountNum and toAccountNum ledger account fields need to be converted to ledger dimension fields.</p></td>
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
<td><p>TaxYearlyComSetupExclude_IT</p></td>
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
<td><p>TaxYearlyComSetupExclude_IT</p></td>
<td><p>FromLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxYearlyComSetupExclude_IT</p></td>
<td><p>ToLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
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
<td><p>TaxYearlyComSetupExclude_IT</p></td>
<td><p>FromAccountNum</p></td>
</tr>
<tr class="even">
<td><p>TaxYearlyComSetupExclude_IT</p></td>
<td><p>ToAccountNum</p></td>
</tr>
</tbody>
</table>

  


