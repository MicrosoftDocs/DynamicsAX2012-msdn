---
title: ReleaseUpdateDB60_Bank.updateLedgerJournalTransRCashRounding Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.updateLedgerJournalTransRCashRounding Upgrade Script
ms:assetid: cbea96c8-62e6-36a2-2c63-4d0f5148d9ec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719682(v=AX.60)
ms:contentKeyID: 49711248
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.updateLedgerJournalTransRCashRounding Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Bank</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateLedgerJournalTransRCashRounding</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Moves data from the DEL_Rounding_HU and DEL_RoundOffAmount_HU fields of the LedgerJournalTrans table to the ManualRounding_HU and RoundOffCashAmount_HU fields of the LedgerJournalTrans_RCash table.</p></td>
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
<tr class="even">
<td><p>Bank</p></td>
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
<td><p>LedgerJournalTrans_RCash</p></td>
</tr>
</tbody>
</table>


## Remarks

The fields are moved from the LedgerJournalTrans table to the cash module specific LedgerJournalTrans\_RCash table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerJournalTrans</p></th>
<th><p>To Table: LedgerJournalTrans_RCash</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Rounding_HU</p></td>
<td><p>ManualRounding_HU</p></td>
</tr>
<tr class="even">
<td><p>DEL_RoundOffAmount_HU</p></td>
<td><p>RoundOffCashAmount_HU</p></td>
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
<td><p>LedgerJournalTrans_RCash</p></td>
<td><p>ManualRounding_HU</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans_RCash</p></td>
<td><p>RoundOffCashAmount_HU</p></td>
<td><p>RoundOff</p></td>
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
<td><p>DEL_Rounding_HU</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
<td><p>DEL_RoundOffAmount_HU</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

