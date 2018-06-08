---
title: ReleaseUpdateDB60_Ledger.updateTaxLedgerAccountGroup Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxLedgerAccountGroup Upgrade Script
ms:assetid: 46547726-f32c-d5d0-2abd-9f28c37c2cef
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718963(v=AX.60)
ms:contentKeyID: 49707997
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxLedgerAccountGroup Upgrade Script 


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
<td><p>updateTaxLedgerAccountGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The TaxAccountUnrealizedPay and TaxAccountUnrealizedRec ledger account fields need to be converted to ledger dimension fields, that is TaxUnrealizedPayablesLedgerDimension and TaxUnrealizedReceivablesLedgerDimension fields.</p></td>
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
<th><p>From Table: TaxLedgerAccountGroup</p></th>
<th><p>To Table: TaxLedgerAccountGroup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CashDiscIncoming</p></td>
<td><p>CashDiscountIncomingLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>CashDiscOutgoing</p></td>
<td><p>CashDiscountOutgoingLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>PennyDiffCust</p></td>
<td><p>PennyDifferenceCustomerLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>PennyDiffVend</p></td>
<td><p>PennyDifferenceVendorLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>TaxAccountFreePct</p></td>
<td><p>TaxFreePercentLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>TaxAccountIncoming</p></td>
<td><p>TaxIncomingLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>TaxAccountOutgoing</p></td>
<td><p>TaxOutgoingLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>TaxAccountReport</p></td>
<td><p>TaxReportLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>TaxAccountUnrealizedPay</p></td>
<td><p>TaxUnrealizedPayablesLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>TaxAccountUnrealizedRec</p></td>
<td><p>TaxUnrealizedReceivablesLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>TaxAccountUseTax</p></td>
<td><p>TaxUseTaxLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>TaxOffsetAccountUseTax</p></td>
<td><p>TaxOffsetUseTaxLedgerDimension</p></td>
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
<td><p>TaxUnrealizedPayablesLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxUnrealizedReceivablesLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>CashDiscountIncomingLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>CashDiscountOutgoingLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>PennyDifferenceCustomerLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>PennyDifferenceVendorLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxFreePercentLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxIncomingLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxOutgoingLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxReportLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxUseTaxLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxOffsetUseTaxLedgerDimension</p></td>
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
<td><p>TaxAccountUnrealizedPay</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxAccountUnrealizedRec</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>CashDiscIncoming</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>CashDiscOutcoming</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>PennyDiffCust</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>PeenyDiffVend</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxAccountFreePct</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxAccountIncoming</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxAccountOutcoming</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxAccountReport</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxAccountUseTax</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TAxOffsetAccountUseTax</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

