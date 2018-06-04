---
title: ReleaseUpdateTransformDB40_Ledger.ledgerJournalControlDeltaPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.ledgerJournalControlDeltaPreProcessing Upgrade Script
ms:assetid: 613d7e44-d1ef-c37b-2a78-57652ca10d64
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719093(v=AX.60)
ms:contentKeyID: 49708633
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.ledgerJournalControlDeltaPreProcessing Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerJournalControlDeltaPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the LedgerJournalControl table data.</p></td>
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
<td><p>LedgerJournalControlHeader</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalControlDetail</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert the account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerJournalControl</p></th>
<th><p>To Table: LedgerJournalControlHeader</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JournalName</p></td>
<td><p>JournalName</p></td>
</tr>
<tr class="even">
<td><p>Company</p></td>
<td><p>JournalLegalEntity</p></td>
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
<th><p>From Table: LedgerJournalControl</p></th>
<th><p>To Table: LedgerJournalControlDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OperationsStatusAll</p></td>
<td><p>LedgerType</p></td>
</tr>
<tr class="even">
<td><p>Company</p></td>
<td><p>LedgerLegalEntity</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

