---
title: ReleaseUpdateDB60_Ledger.updateLedgerJournalTransPayment_LV Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerJournalTransPayment_LV Upgrade Script
ms:assetid: 468bdd7c-33aa-defc-5758-c203c5eba7a5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718966(v=AX.60)
ms:contentKeyID: 49707999
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerJournalTransPayment\_LV Upgrade Script 


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
<td><p>updateLedgerJournalTransPayment_LV</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transfers LV payment order specific fields from the LedgerJournalTrans table to the LedgerJournalTransPayment_LV table.</p></td>
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
<td><p>LedgerJournalTransPayment_LV</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>LvPaymentOrderInfo</p></td>
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
<th><p>From Table: LedgerJournalTrans</p></th>
<th><p>To Table: LedgerJournalTransPayment_LV</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BankCommissionPayer_LV</p></td>
<td><p>BankCommissionPayer_LV</p></td>
</tr>
<tr class="even">
<td><p>IntBankCommissionPayer_LV</p></td>
<td><p>IntBankCommissionPayer_LV</p></td>
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
<td><p>LedgerJournalTransPayment_LV</p></td>
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
<td><p>LedgerJournalTrans</p></td>
<td><p>BankCommissionPayer_LV</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
<td><p>IntBankCommissionPayer_LV</p></td>
</tr>
</tbody>
</table>

  


