---
title: ReleaseUpdateTransformDB40_LedgerTrx.ledgerTransPreProcessingDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_LedgerTrx.ledgerTransPreProcessingDelta Upgrade Script
ms:assetid: 8e4f7598-ec60-cd9c-b7b7-48e1f6c7de4c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736505(v=AX.60)
ms:contentKeyID: 49709694
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_LedgerTrx.ledgerTransPreProcessingDelta Upgrade Script 


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
<td><p>ledgerTransPreProcessingDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the delta pre-processing of records in the LedgerTrans table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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
</tbody>
</table>


## Remarks

Each LedgerTrans record will be normalized across the LedgerEntryJournal, GeneralJournalEntry, GeneralJournalAccountEntry, LedgerEntry, and LedgerEntryJournalizing tables. This is a sergeant method that calls the other associated methods to preform this normalization against each record in the LedgerTrans table that has been created, updated, or deleted since the live pre-processing step of the upgrade was run.

  


