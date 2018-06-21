---
title: ReleaseUpdateTransformDB40_LedgerTrx.ledgerTransLedgerEntryJournal Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_LedgerTrx.ledgerTransLedgerEntryJournal Upgrade Script
ms:assetid: ab8a65c5-bc18-7efe-c734-6fc800e56941
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686481(v=AX.60)
ms:contentKeyID: 49710436
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_LedgerTrx.ledgerTransLedgerEntryJournal Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_LedgerTrx</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerTransLedgerEntryJournal</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the live pre-processing population of records in the LedgerEntryJournal table based upon existing records in the LedgerTrans table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>LedgerTrans</p></td>
</tr>
<tr class="even">
<td><p>LedgerEntryJournal</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a helper method that is called by the main live preprocessing script and delta script for the LedgerTrans table. The LedgerEntryJournal table will contain one record for every unique JournalNumber value found in the LedgerTrans.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerTrans</p></th>
<th><p>To Table: LedgerEntryJournal</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JournalNum</p></td>
<td><p>JournalNum</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

