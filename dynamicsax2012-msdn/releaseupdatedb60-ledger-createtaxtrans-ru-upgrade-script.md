---
title: ReleaseUpdateDB60_Ledger.createTaxTrans_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.createTaxTrans_RU Upgrade Script
ms:assetid: 8d874c4b-fdbc-b573-6373-68fc2989d267
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736482(v=AX.60)
ms:contentKeyID: 49709671
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.createTaxTrans\_RU Upgrade Script 


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
<td><p>createTaxTrans_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates Russia country specific fields from the TaxTrans table to the TaxTrans_RU table.</p></td>
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
<td><p>TaxTrans_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
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
<td><p>TaxTrans_RU</p></td>
<td><p>CustVendTransPostingLog_RU</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_RU</p></td>
<td><p>GoodsInRouteId_RU</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_RU</p></td>
<td><p>GoodsInRouteToDelivery_RU</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_RU</p></td>
<td><p>MarkupTransRecId_RU</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_RU</p></td>
<td><p>OffsetLedgerDimension_RU</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_RU</p></td>
<td><p>TaxSourceType_RU</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_RU</p></td>
<td><p>TaxUnroundAmount_RU</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_RU</p></td>
<td><p>TaxUnroundAmountCur_RU</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans_RU</p></td>
<td><p>VATOperationCode_RU</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxTrans_RU</p></td>
<td><p>VATTaxAgentVendAccount_RU</p></td>
<td><p></p></td>
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
<td><p>TaxTrans</p></td>
<td><p>CustVendTransPostingLog_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>GoodsInRouteId_RU</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>GoodsInRouteToDelivery_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>MarkupTransRecId_RU</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>OffsetLedgerDimension_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>TaxSourceType_RU</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>TaxUnroundAmount_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>TaxUnroundAmountCur_RU</p></td>
</tr>
<tr class="odd">
<td><p>TaxTrans</p></td>
<td><p>vatOperationCode_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxTrans</p></td>
<td><p>vatTaxAgentVendAccount_RU</p></td>
</tr>
</tbody>
</table>

  


