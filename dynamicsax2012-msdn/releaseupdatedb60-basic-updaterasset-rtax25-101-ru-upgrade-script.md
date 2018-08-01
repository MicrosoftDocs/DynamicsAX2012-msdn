---
title: ReleaseUpdateDB60_Basic.updateRAsset_RTax25_101_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateRAsset_RTax25_101_RU Upgrade Script
ms:assetid: 614ffe61-041e-9063-9228-f9eac8df4c39
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719096(v=AX.60)
ms:contentKeyID: 49708636
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateRAsset\_RTax25\_101\_RU Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateRAsset_RTax25_101_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates the key fields of the RAsset and RTax25 tables to the 101 relation model.</p></td>
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
<td><p>Fixed Asset</p></td>
</tr>
<tr class="even">
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
<td><p>RAssetInferiorDisposalTable</p></td>
</tr>
<tr class="even">
<td><p>RAssetInferiorDisposalTrans</p></td>
</tr>
<tr class="odd">
<td><p>RAssetInventIssueTable</p></td>
</tr>
<tr class="even">
<td><p>RAssetInventIssueTrans</p></td>
</tr>
<tr class="odd">
<td><p>RAssetInventIssueQuotaTypes</p></td>
</tr>
<tr class="even">
<td><p>RAssetTable</p></td>
</tr>
<tr class="odd">
<td><p>RAssetInventIssueQuotas</p></td>
</tr>
<tr class="even">
<td><p>RAssetTaxAllowanceHistory</p></td>
</tr>
<tr class="odd">
<td><p>RAssetTaxAllowance</p></td>
</tr>
<tr class="even">
<td><p>RTax25TaxTable</p></td>
</tr>
<tr class="odd">
<td><p>RAssetDeprProfile</p></td>
</tr>
<tr class="even">
<td><p>RAssetLifeHist</p></td>
</tr>
<tr class="odd">
<td><p>RAssetStandards</p></td>
</tr>
<tr class="even">
<td><p>RAssetGroup</p></td>
</tr>
<tr class="odd">
<td><p>RAssetDeprProfileTrans</p></td>
</tr>
<tr class="even">
<td><p>RTax25StdRateTable</p></td>
</tr>
<tr class="odd">
<td><p>RTax25StdRateTrans</p></td>
</tr>
<tr class="even">
<td><p>RTax25LedgerIntervalGroup</p></td>
</tr>
<tr class="odd">
<td><p>RTax25LedgerInterval</p></td>
</tr>
<tr class="even">
<td><p>RTax25ProfitTable</p></td>
</tr>
<tr class="odd">
<td><p>AdvanceAdjustmentParameters_W</p></td>
</tr>
<tr class="even">
<td><p>Currency_W</p></td>
</tr>
<tr class="odd">
<td><p>CustParameters</p></td>
</tr>
<tr class="even">
<td><p>VendParameters</p></td>
</tr>
<tr class="odd">
<td><p>AmountDiffParameters_RU</p></td>
</tr>
<tr class="even">
<td><p>EmplParameters_RU</p></td>
</tr>
<tr class="odd">
<td><p>RAssetDeferralsAccounts</p></td>
</tr>
<tr class="even">
<td><p>RDeferralsTable</p></td>
</tr>
<tr class="odd">
<td><p>RDeferralsWritingOffFactor</p></td>
</tr>
<tr class="even">
<td><p>RTax25RegisterTrans</p></td>
</tr>
<tr class="odd">
<td><p>RTax25StdExpressionLine</p></td>
</tr>
<tr class="even">
<td><p>RTax25StdExpressionTable</p></td>
</tr>
<tr class="odd">
<td><p>RTax25ProfitTotalsSetup</p></td>
</tr>
<tr class="even">
<td><p>RTax25RegisterProfit</p></td>
</tr>
<tr class="odd">
<td><p>RTax25ProfitLedgerSetup</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

