---
title: ReleaseUpdateDB60_Vend.updateVendLedgerAccounts Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendLedgerAccounts Upgrade Script
ms:assetid: 63e579f4-2437-a7b7-95a8-daa720f6fb48
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719147(v=AX.60)
ms:contentKeyID: 49708686
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendLedgerAccounts Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateVendLedgerAccounts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the old account and dimension fields to the new account and dimension fields in the VendLedgerAccounts table.</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>VendLedgerAccounts</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert the account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendLedgerAccounts</p></th>
<th><p>To Table: VendLedgerAccounts</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ClearingAccount</p></td>
<td><p>ClearingLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>PurchLedgerAccount</p></td>
<td><p>PurchasingLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>PurchLedgerOffsetAccount</p></td>
<td><p>PurchasingOffsetLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>SumAccount</p></td>
<td><p>SummaryLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>VATprepaymentsAccount</p></td>
<td><p>VATPrepaymentsLedgerDimension</p></td>
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
<td><p>VendLedgerAccounts</p></td>
<td><p>ClearingLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>VendLedgerAccounts</p></td>
<td><p>PurchasingLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>VendLedgerAccounts</p></td>
<td><p>PurchasingOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>VendLedgerAccounts</p></td>
<td><p>SummaryLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>VendLedgerAccounts</p></td>
<td><p>VATPrepaymentsLedgerDimension</p></td>
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
<td><p>VendLedgerAccounts</p></td>
<td><p>ClearingAccount</p></td>
</tr>
<tr class="even">
<td><p>VendLedgerAccounts</p></td>
<td><p>PurchLedgerAccount</p></td>
</tr>
<tr class="odd">
<td><p>VendLedgerAccounts</p></td>
<td><p>PurchLedgerOffsetAccount</p></td>
</tr>
<tr class="even">
<td><p>VendLedgerAccounts</p></td>
<td><p>SumAccount</p></td>
</tr>
<tr class="odd">
<td><p>VendLedgerAccounts</p></td>
<td><p>VATPrepaymentsAccount</p></td>
</tr>
</tbody>
</table>

  


