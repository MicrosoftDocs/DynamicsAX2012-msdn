---
title: ReleaseUpdateDB60_Bank.updateExchAdjPL Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.updateExchAdjPL Upgrade Script
ms:assetid: cf908408-9805-73d6-84fb-e5570f817c5d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686885(v=AX.60)
ms:contentKeyID: 49711336
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.updateExchAdjPL Upgrade Script [AX 2012]


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
<td><p>updateExchAdjPL</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades script for the exchange adjustment feature for PL.</p></td>
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
<td><p>Bank</p></td>
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
<td><p>BankAccountTransPL</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans_RCash</p></td>
</tr>
</tbody>
</table>


## Remarks

The upgrade script is necessary due to the following changes in the data model from previous version. 1. The country specific fields have been moved from the BankAccounTrans table to the BankAccountTransPL table. 2. The country specific fields have been moved from the ledgerJournalTrans table to the LedgerJournalTrans\_RCash table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerJournalTrans</p></th>
<th><p>To Table: LedgerJournalTrans_Rcash</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_ExcludeExchAdj_PL</p></td>
<td><p>ExcludeExchAdj_PL</p></td>
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
<th><p>From Table: BankAccountTrans</p></th>
<th><p>To Table: BankAccountTransPL</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_ExchAdjustment_PL</p></td>
<td><p>ExchAdjustment_PL</p></td>
</tr>
<tr class="even">
<td><p>DEL_ExcludeExchAdj_PL</p></td>
<td><p>ExcludeExchAdj_PL</p></td>
</tr>
<tr class="odd">
<td><p>DEL_SettleAmountCur_PL</p></td>
<td><p>SettleAmountCur_PL</p></td>
</tr>
<tr class="even">
<td><p>DEL_SettleAmountMST_PL</p></td>
<td><p>SettleAmountMST_PL</p></td>
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
<td><p>BankAccountTrans</p></td>
<td><p>DEL_ExchAdjustment_PL</p></td>
</tr>
<tr class="even">
<td><p>BankAccountTrans</p></td>
<td><p>DEL_ExcludeExchAdj_PL</p></td>
</tr>
<tr class="odd">
<td><p>BankAccountTrans</p></td>
<td><p>DEL_SettleAmountCur_PL</p></td>
</tr>
<tr class="even">
<td><p>BankAccountTrans</p></td>
<td><p>DEL_SettleAmountMST_PL</p></td>
</tr>
<tr class="odd">
<td><p>LedgerJournalTrans</p></td>
<td><p>DEL_ExcludeExchAdj_PL</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

