---
title: ReleaseUpdateDB60_Ledger.updateTaxPurchaseTaxTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxPurchaseTaxTable Upgrade Script
ms:assetid: 86cd66b7-a7ea-a9e8-0918-ee47c441930f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686065(v=AX.60)
ms:contentKeyID: 49709516
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxPurchaseTaxTable Upgrade Script [AX 2012]


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
<td><p>updateTaxPurchaseTaxTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the ExpenseAccount, SettleAccount, and TaxAccount fields to the ExpenseLedgerDimension, SettleLedgerDimension, and TaxLedgerDimension fields, respectively, in the TaxPurchaseTaxTable table.</p></td>
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
<td><p>TaxPurchaseTaxTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account or dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TaxPurchaseTaxTable</p></th>
<th><p>To Table: TaxPurchaseTaxTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExpenseAccount</p></td>
<td><p>ExpenseLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>SettleAccount</p></td>
<td><p>SettleLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>TaxAccount</p></td>
<td><p>TaxLedgerDimension</p></td>
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
<td><p>TaxPurchaseTaxTable</p></td>
<td><p>ExpenseLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxPurchaseTaxTable</p></td>
<td><p>SettleLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxPurchaseTaxTable</p></td>
<td><p>TaxLedgerDimension</p></td>
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
<td><p>TaxPurchaseTaxTable</p></td>
<td><p>ExpenseAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxPurchaseTaxTable</p></td>
<td><p>SettleAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxPurchaseTaxTable</p></td>
<td><p>TaxAccount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

