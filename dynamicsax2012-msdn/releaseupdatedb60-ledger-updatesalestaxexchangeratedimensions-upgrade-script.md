---
title: ReleaseUpdateDB60_Ledger.updateSalesTaxExchangeRateDimensions Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateSalesTaxExchangeRateDimensions Upgrade Script
ms:assetid: e19c99d8-e5f2-0453-34a2-6ea9b5be6050
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737325(v=AX.60)
ms:contentKeyID: 49711768
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateSalesTaxExchangeRateDimensions Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateSalesTaxExchangeRateDimensions</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the VAT exchange rate difference ledger dimensions of the TaxLedgerAccountGroup table using the old main accounts.</p></td>
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
<td><p>TaxLedgerAccountGroup</p></td>
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
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxIncomingDifferenceLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxOutgoingDifferenceLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxOutgoingDiffOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxIncomingDiffOffsetLedgerDimension</p></td>
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
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>Del_TaxAccountIncomingDisc_W</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>Del_TaxAccountOutgoingDisc_W</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>Ddel_TaxAccountOutgoingDiscOffset_W</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>Del_TaxAccountIncomingDiscOffset_W</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

