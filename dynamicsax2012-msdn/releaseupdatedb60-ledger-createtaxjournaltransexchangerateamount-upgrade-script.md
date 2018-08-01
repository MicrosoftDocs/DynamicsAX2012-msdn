---
title: ReleaseUpdateDB60_Ledger.createTaxJournalTransExchangeRateAmount Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.createTaxJournalTransExchangeRateAmount Upgrade Script
ms:assetid: 4f0f4f82-5790-1f12-01d0-464bc975df4d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685487(v=AX.60)
ms:contentKeyID: 49708191
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.createTaxJournalTransExchangeRateAmount Upgrade Script 


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
<td><p>createTaxJournalTransExchangeRateAmount</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the TaxJournalTransExchangeRateAmount table from the TaxJournalTrans table.</p></td>
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
<td><p>TaxJournalTransExchangeRateAmount</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TaxJournalTrans</p></th>
<th><p>To Table: TaxJournalTransExchangeRateAmount</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>TaxJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>Del_TaxAmount_W</p></td>
<td><p>ExchangeRateTaxAmount</p></td>
</tr>
<tr class="odd">
<td><p>Del_TaxBaseAmount_W</p></td>
<td><p>ExchangeRateTaxBaseAmount</p></td>
</tr>
<tr class="even">
<td><p>Del_SourceBaseAmountRegulated_W</p></td>
<td><p>ExchangeRateSourceBaseAmountRegulated</p></td>
</tr>
<tr class="odd">
<td><p>Del_SourceRegulateAmount_W</p></td>
<td><p>ExchangeRateSourceRegulateAmount</p></td>
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
<td><p>TaxJournalTransExchangeRateAmount</p></td>
<td><p></p></td>
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
<td><p>TaxJournalTrans</p></td>
<td><p>Del_TaxAmount_W</p></td>
</tr>
<tr class="even">
<td><p>TaxJournalTrans</p></td>
<td><p>Del_TaxBaseAmount_W</p></td>
</tr>
<tr class="odd">
<td><p>TaxJournalTrans</p></td>
<td><p>Del_SourceBaseAmountRegulated_W</p></td>
</tr>
<tr class="even">
<td><p>TaxJournalTrans</p></td>
<td><p>Del_SourceRegulateAmount_W</p></td>
</tr>
</tbody>
</table>

  


