---
title: ReleaseUpdateDB60_Ledger.updateCurrency_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateCurrency_W Upgrade Script
ms:assetid: 364f4689-6fdd-5660-2b7c-013e16676084
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685166(v=AX.60)
ms:contentKeyID: 49707619
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateCurrency\_W Upgrade Script 


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
<td><p>updateCurrency_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the new Currency_W table with the information from the fields in the Currency table that are being deleted.</p></td>
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
<td><p>Currency_W</p></td>
</tr>
</tbody>
</table>


## Remarks

If it is necessary this upgrade converts account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: Currency</p></th>
<th><p>To Table: Currency</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CurrencyCode</p></td>
<td><p>CurrencyCode</p></td>
</tr>
<tr class="even">
<td><p>del_TaxAmountDiffLedgerAccount_RU</p></td>
<td><p>TaxAmountDiffLedgerDimension_RU</p></td>
</tr>
<tr class="odd">
<td><p>del_TaxAmountDiffLedgerAccountLoss_RU</p></td>
<td><p>TaxAmountDiffLossLedgerDimension_RU</p></td>
</tr>
<tr class="even">
<td><p>del_TaxAmountDiffLedgerAccountProfit_RU</p></td>
<td><p>TaxAmountDiffProfitLedgerDimension_RU</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountNonrealProfitCust_W</p></td>
<td><p>UnrealizedProfitCustLedgerDimension_W</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountNonrealLossCust_W</p></td>
<td><p>UnrealizedLossCustLedgerDimension_W</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountProfitCust_W</p></td>
<td><p>RealizedProfitCustLedgerDimension_W</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountLossCust_W</p></td>
<td><p>RealizedLossCustLedgerDimension_W</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountNonrealProfitVend_W</p></td>
<td><p>UnrealizedProfitVendLedgerDimension_W</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountNonrealLossVend_W</p></td>
<td><p>UnrealizedLossVendLedgerDimension_W</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountLossVend_W</p></td>
<td><p>RealizedLossVendLedgerDimension_W</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountProfitVend_W</p></td>
<td><p>RealizedProfitVendLedgerDimension_W</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountProfitTaxVend_W</p></td>
<td><p>RealizedProfitTaxVendLedgerDimension_W</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountLossTaxVend_W</p></td>
<td><p>RealizedLossTaxVendLedgerDimension_W</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountLossTaxCust_W</p></td>
<td><p>RealizedLossTaxCustLedgerDimension_W</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountProfitTaxCust_W</p></td>
<td><p>RealizedProfitTaxCustLedgerDimension_W</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountNonrealLossTaxCust_W</p></td>
<td><p>UnrealizedLossTaxCustLedgerDimension_W</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountNonrealProfitTaxCust_W</p></td>
<td><p>UnrealizedProfitTaxCustLedgerDimension_W</p></td>
</tr>
<tr class="odd">
<td><p>del_LedgerAccountFinLoss_W</p></td>
<td><p>FinLossLedgerDimension_W</p></td>
</tr>
<tr class="even">
<td><p>del_LedgerAccountFinProfit_W</p></td>
<td><p>FinProfitLedgerDimension_W</p></td>
</tr>
<tr class="odd">
<td><p>del_TaxAmountDifference_RU</p></td>
<td><p>TaxAmountDifference_RU</p></td>
</tr>
<tr class="even">
<td><p>del_ExchRateNonrealProfitTaxCust_W</p></td>
<td><p>ExchRateNonrealProfitTaxCust_W</p></td>
</tr>
<tr class="odd">
<td><p>del_ExchRateNonrealLossTaxCust_W</p></td>
<td><p>ExchRateNonrealLossTaxCust_W</p></td>
</tr>
<tr class="even">
<td><p>del_ExchRateProfitTaxVend_W</p></td>
<td><p>ExchRateProfitTaxVend_W</p></td>
</tr>
<tr class="odd">
<td><p>del_ExchRateLossTaxVend_W</p></td>
<td><p>ExchRateLossTaxVend_W</p></td>
</tr>
<tr class="even">
<td><p>del_CustPostingMode_W</p></td>
<td><p>CustPostingMode_W</p></td>
</tr>
<tr class="odd">
<td><p>del_CustPostingModeTax_W</p></td>
<td><p>CustPostingModeTax_W</p></td>
</tr>
<tr class="even">
<td><p>del_VendPostingMode_W</p></td>
<td><p>VendPostingMode_W</p></td>
</tr>
<tr class="odd">
<td><p>del_VendPostingModeTax_W</p></td>
<td><p>VendPostingModeTax_W</p></td>
</tr>
<tr class="even">
<td><p>del_ExchRateNeg_RU</p></td>
<td><p>ExchRateNeg_RU</p></td>
</tr>
<tr class="odd">
<td><p>del_ExchRatePos_RU</p></td>
<td><p>ExchRatePos_RU</p></td>
</tr>
<tr class="even">
<td><p>del_rTax25ProfitIdProfitVend</p></td>
<td><p>del_rTax25ProfitIdProfitVend</p></td>
</tr>
<tr class="odd">
<td><p>del_rTax25ProfitIdProfitCust</p></td>
<td><p>del_rTax25ProfitIdProfitCust</p></td>
</tr>
<tr class="even">
<td><p>del_rTax25ProfitIdLossVend</p></td>
<td><p>del_rTax25ProfitIdLossVend</p></td>
</tr>
<tr class="odd">
<td><p>del_rTax25ProfitIdLossCust</p></td>
<td><p>del_rTax25ProfitIdLossCust</p></td>
</tr>
<tr class="even">
<td><p>del_rTax25ProfitIdProfit</p></td>
<td><p>del_rTax25ProfitIdProfit</p></td>
</tr>
<tr class="odd">
<td><p>del_rTax25ProfitIdLoss</p></td>
<td><p>del_rTax25ProfitIdLoss</p></td>
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
<td><p>Currency_W</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


