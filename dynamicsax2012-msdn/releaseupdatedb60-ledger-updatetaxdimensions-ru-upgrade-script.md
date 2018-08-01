---
title: ReleaseUpdateDB60_Ledger.updateTaxDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxDimensions_RU Upgrade Script
ms:assetid: b84db528-ffa0-cfa5-668d-6038ffc20ac9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737078(v=AX.60)
ms:contentKeyID: 49710760
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxDimensions\_RU Upgrade Script 


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
<td><p>updateTaxDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from account fields to the LedgerDimension fields in the TaxLedgerAccountGroup table.</p></td>
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

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

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
<td><p>del_TaxFineAccount_RU</p></td>
<td><p>TaxFineLedgerDimension_RU</p></td>
</tr>
<tr class="even">
<td><p>del_TaxOffsetAccountOutgoing_RU</p></td>
<td><p>TaxOutgoingOffsetLedgerDimension_RU</p></td>
</tr>
<tr class="odd">
<td><p>del_TaxAccountDeferred_RU</p></td>
<td><p>TaxDeferredLedgerDimension_RU</p></td>
</tr>
<tr class="even">
<td><p>del_TaxIncomingPayment_RU</p></td>
<td><p>TaxIncomingPaymentLedgerDimension_RU</p></td>
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
<td><p>TaxFineLedgerDimension_RU</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxOutgoingOffsetLedgerDimension_RU</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxDeferredLedgerDimension_RU</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxIncomingPaymentLedgerDimension_RU</p></td>
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
<td><p>TaxFineAccount_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxOffsetAccountOutgoing_RU</p></td>
</tr>
<tr class="odd">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxAccountDeferred_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxLedgerAccountGroup</p></td>
<td><p>TaxIncomingPayment_RU</p></td>
</tr>
</tbody>
</table>

  


