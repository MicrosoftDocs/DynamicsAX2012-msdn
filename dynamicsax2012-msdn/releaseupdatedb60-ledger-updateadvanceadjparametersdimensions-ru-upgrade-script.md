---
title: ReleaseUpdateDB60_Ledger.updateAdvanceAdjParametersDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateAdvanceAdjParametersDimensions_RU Upgrade Script
ms:assetid: 1c6f1e66-74a2-d0ae-7fee-1b01d112bfd3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718705(v=AX.60)
ms:contentKeyID: 49706988
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateAdvanceAdjParametersDimensions\_RU Upgrade Script [AX 2012]


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
<td><p>updateAdvanceAdjParametersDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts data from the old account fields to the new LedgerDimension field in the AdvanceAdjustmentParameters_W table.</p></td>
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
<td><p>AdvanceAdjustmentParameters_W</p></td>
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
<th><p>From Table: AdvanceAdjustmentParameters_W</p></th>
<th><p>To Table: AdvanceAdjustmentParameters_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_LedgerAccountProfitCust</p></td>
<td><p>ProfitCustLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountLossCust</p></td>
<td><p>LossCustLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountLossVend</p></td>
<td><p>LossVendLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountProfitVend</p></td>
<td><p>ProfitVendLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>del_rTax25LedgerAccountCustLoss</p></td>
<td><p>rTax25CustLossLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_rTax25LedgerAccountCustProfit</p></td>
<td><p>rTax25CustProfitLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>del_rTax25OffsetLedgerAccountCust</p></td>
<td><p>rTax25OffsetLedgerDimensionCust</p></td>
</tr>
<tr class="even">
<td><p>del_rTax25LedgerAccountVendLoss</p></td>
<td><p>rTax25VendLossLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>del_rTax25LedgerAccountVendProfit</p></td>
<td><p>rTax25VendProfitLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_rTax25OffsetLedgerAccountVend</p></td>
<td><p>rTax25OffsetLedgerDimensionVend</p></td>
</tr>
<tr class="odd">
<td><p>del_vatAdjustmentProfitCust</p></td>
<td><p>vatAdjustmentProfitCustLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>del_vatAdjustmentLossCust</p></td>
<td><p>vatAdjustmentLossCustLedgerDimension</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

