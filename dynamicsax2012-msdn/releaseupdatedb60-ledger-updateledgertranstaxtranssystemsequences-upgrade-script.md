---
title: ReleaseUpdateDB60_Ledger.updateLedgerTransTaxTransSystemSequences Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerTransTaxTransSystemSequences Upgrade Script
ms:assetid: d65c8e21-2233-edb5-815d-918dcaf5ae20
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687067(v=AX.60)
ms:contentKeyID: 49711515
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerTransTaxTransSystemSequences Upgrade Script 


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
<td><p>updateLedgerTransTaxTransSystemSequences</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the entries in the SystemSequences table to ensure the RecId value of any new record does not conflict with the values that were generated during the PreUpgrade process.</p></td>
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
<td><p>SystemSequences</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalHeader</p></td>
</tr>
<tr class="odd">
<td><p>LedgerEntryJournal</p></td>
</tr>
<tr class="even">
<td><p>LedgerEntryReference</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalLine</p></td>
</tr>
<tr class="even">
<td><p>LedgerEntry</p></td>
</tr>
<tr class="odd">
<td><p>LedgerEntryJournalizing</p></td>
</tr>
<tr class="even">
<td><p>TaxTransLedgerEntry</p></td>
</tr>
</tbody>
</table>

  


