---
title: ReleaseUpdateTransformDB50_LedgerTrx.ledgerTransLedgerEntryJournalizing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_LedgerTrx.ledgerTransLedgerEntryJournalizing Upgrade Script
ms:assetid: ceb8806c-e182-cf2a-98a4-c93456a3f1d7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719758(v=AX.60)
ms:contentKeyID: 49711324
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_LedgerTrx.ledgerTransLedgerEntryJournalizing Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_LedgerTrx</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerTransLedgerEntryJournalizing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the live pre-processing population of records in the LedgerEntryJournalizing table based on existing records in the LedgerTrans table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>LedgerEntryJournalizing</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a helper method that is called by the main live preprocessing script and delta script for the LedgerTrans table. The LedgerEntryJournalizing table will contain one record for every record found in the LedgerTrans table that contains a value for the JournalizeNum.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerTrans</p></th>
<th><p>To Table: LedgerEntryJournalizing</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JournalizeNum</p></td>
<td><p>Journal</p></td>
</tr>
<tr class="even">
<td><p>JournalizeSeqNum</p></td>
<td><p>SequenceNumber</p></td>
</tr>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DEL_LedgerTransRefRecId</p></td>
</tr>
<tr class="even">
<td><p>DataAreaId</p></td>
<td><p>DEL_DataAreaId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: GeneralJournalAccountEntry</p></th>
<th><p>To Table: LedgerEntryJournalizing</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

