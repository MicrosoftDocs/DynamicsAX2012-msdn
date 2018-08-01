---
title: ReleaseUpdateDB60_Vend.createVendTrans_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createVendTrans_W Upgrade Script
ms:assetid: 50c9a854-ae36-4b1d-8fa9-4c7992493677
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685529(v=AX.60)
ms:contentKeyID: 49708232
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createVendTrans\_W Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>createVendTrans_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country specific fields from &lt;c&gt;VendTrans&lt;/c&gt; table to &lt;c&gt;VendTrans_W&lt;/c&gt; table</p></td>
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
<td><p>VendTrans</p></td>
</tr>
<tr class="even">
<td><p>VendTrans_W</p></td>
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
<th><p>From Table: VendTrans</p></th>
<th><p>To Table: VendTrans_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdvancePayment_IN</p></td>
<td><p>AdvancePayment_IN</p></td>
</tr>
<tr class="even">
<td><p>BankCurrencyTransferId_RU</p></td>
<td><p>BankCurrencyTransferId_RU</p></td>
</tr>
<tr class="odd">
<td><p>CorrectReporting_RU</p></td>
<td><p>CorrectReporting_RU</p></td>
</tr>
<tr class="even">
<td><p>DefaultDimensionReporting_RU</p></td>
<td><p>DefaultDimensionReporting_RU</p></td>
</tr>
<tr class="odd">
<td><p>EmplAccount_RU</p></td>
<td><p>EmplAccount_RU</p></td>
</tr>
<tr class="even">
<td><p>GTARecoverableAmount_IN</p></td>
<td><p>GTARecoverableAmount_IN</p></td>
</tr>
<tr class="odd">
<td><p>PrepaymentFactureId_W</p></td>
<td><p>PrepaymentFactureId_W</p></td>
</tr>
<tr class="even">
<td><p>RefVoucher_IN</p></td>
<td><p>RefVoucher_IN</p></td>
</tr>
<tr class="odd">
<td><p>RTax25Amortisation</p></td>
<td><p>RTax25Amortisation_RU</p></td>
</tr>
<tr class="even">
<td><p>Settlement_IN</p></td>
<td><p>Settlement_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxComponentTable_IN</p></td>
<td><p>TaxComponentTable_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdAmountOrigin_IN</p></td>
<td><p>TaxWithholdAmountOrigin_IN</p></td>
</tr>
<tr class="odd">
<td><p>TCSAmount_IN</p></td>
<td><p>TCSAmount_IN</p></td>
</tr>
<tr class="even">
<td><p>TDSAmount_IN</p></td>
<td><p>TDSAmount_IN</p></td>
</tr>
</tbody>
</table>

  


