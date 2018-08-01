---
title: ReleaseUpdateDB41_Ledger.createLedgerJournalTrans_RAsset Upgrade Script
TOCTitle: ReleaseUpdateDB41_Ledger.createLedgerJournalTrans_RAsset Upgrade Script
ms:assetid: 1044e6b6-9c0c-173d-db19-02c1ee39af2f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735778(v=AX.60)
ms:contentKeyID: 49706675
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Ledger.createLedgerJournalTrans\_RAsset Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createLedgerJournalTrans_RAsset</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the LedgerJournalTrans_RAsset table from the LedgerJournalTrans table.</p></td>
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
<td><p>LedgerJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans_RAsset</p></td>
</tr>
</tbody>
</table>


## Remarks

The asset specific fields are being removed from the LedgerJournalTrans table for this release. These fields are being moved to the LedgerJournalTrans\_RAsset table and linked by the LedgerJournalTrans record ID.

  


