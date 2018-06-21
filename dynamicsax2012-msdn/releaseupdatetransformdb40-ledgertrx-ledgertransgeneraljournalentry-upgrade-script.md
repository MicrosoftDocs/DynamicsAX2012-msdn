---
title: ReleaseUpdateTransformDB40_LedgerTrx.ledgerTransGeneralJournalEntry Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_LedgerTrx.ledgerTransGeneralJournalEntry Upgrade Script
ms:assetid: b10828fe-cc87-5c0d-b739-ca85ec2692eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736879(v=AX.60)
ms:contentKeyID: 49710564
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_LedgerTrx.ledgerTransGeneralJournalEntry Upgrade Script [AX 2012]


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
<td><p>ledgerTransGeneralJournalEntry</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the live pre-processing population of records in the GeneralJournalEntry table that is based upon existing records in the LedgerTrans table.</p></td>
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
<td><p>GeneralJournalEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a helper method that is called by the main live preprocessing script and delta script for the LedgerTrans table. The GeneralJournalEntry table will contain one record for every unique JournalNumber, LedgerPostingJournal, PeriodCode, OperationsTax, and Voucher value in the LedgerTrans table. This also creates a record in the subledgerVoucherGeneralJournalEntry table for an end record that is created in the GeneralJournalEntry table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

