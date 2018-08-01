---
title: ReleaseUpdateDB60_Ledger.updateAmountDiffParametersDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateAmountDiffParametersDimensions_RU Upgrade Script
ms:assetid: e4654fbe-db72-d212-3bd4-2e99d89cb7bc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719760(v=AX.60)
ms:contentKeyID: 49711834
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateAmountDiffParametersDimensions\_RU Upgrade Script 


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
<td><p>updateAmountDiffParametersDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts data from the old account fields to the new LedgerDimension field in the AmountDiffParameters_RU table.</p></td>
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
<td><p>AmountDiffParameters_RU</p></td>
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
<th><p>From Table: AmountDiffParameters_RU</p></th>
<th><p>To Table: AmountDiffParameters_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_TaxAmountDiffLedgerAccount</p></td>
<td><p>TaxAmountDiffLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_CustLedgerAccountProfit</p></td>
<td><p>RealizedProfitCustLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>del_CustLedgerAccountLoss</p></td>
<td><p>RealizedLossCustLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_CustLedgerAccountNonrealProfit</p></td>
<td><p>UnrealizedProfitCustLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>del_CustLedgerAccountNonrealLoss</p></td>
<td><p>UnrealizedLossCustLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_VendLedgerAccountProfit</p></td>
<td><p>RealizedProfitVendLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>del_VendLedgerAccountLoss</p></td>
<td><p>RealizedLossVendLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_VendLedgerAccountNonrealProfit</p></td>
<td><p>UnrealizedProfitVendLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>del_VendLedgerAccountNonrealLoss</p></td>
<td><p>UnrealizedLossVendLedgerDimension</p></td>
</tr>
</tbody>
</table>

  


