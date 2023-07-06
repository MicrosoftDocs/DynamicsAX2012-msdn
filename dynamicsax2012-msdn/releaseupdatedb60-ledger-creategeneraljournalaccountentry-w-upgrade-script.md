---
title: ReleaseUpdateDB60_Ledger.createGeneralJournalAccountEntry_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.createGeneralJournalAccountEntry_W Upgrade Script
ms:assetid: a655977e-f7f8-e51a-c54a-c155c0b88868
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736856(v=AX.60)
ms:contentKeyID: 49710287
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.createGeneralJournalAccountEntry\_W Upgrade Script 


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
<td><p>createGeneralJournalAccountEntry_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Moves country/region specific data from the GeneralJournalAccountEntry table to the GeneralJournalAccountEntry_W table.</p></td>
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
<td><p>GeneralJournalAccountEntry_W</p></td>
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
<td><p>GeneralJournalAccountEntry_W</p></td>
<td><p>BondBatchTrans_RU</p></td>
<td><p>LedgerBondBatchTransNum_RU</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalAccountEntry_W</p></td>
<td><p>ConsolidatedRefRecId_BR</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalAccountEntry_W</p></td>
<td><p>ConsolidatedVoucher_BR</p></td>
<td><p>Voucher</p></td>
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
<td><p>GeneralJournalAccountEntry</p></td>
<td><p>BondBatchTrans_RU</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalAccountEntry</p></td>
<td><p>ConsolidatedRefRecId_BR</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalAccountEntry</p></td>
<td><p>ConsolidatedVoucher_BR</p></td>
</tr>
</tbody>
</table>

  


