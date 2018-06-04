---
title: ReleaseUpdateDB60_Ledger.createGeneralJournalEntry_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.createGeneralJournalEntry_W Upgrade Script
ms:assetid: 8b0f519d-f6e6-6624-4433-b7a7bd434265
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736419(v=AX.60)
ms:contentKeyID: 49709608
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.createGeneralJournalEntry\_W Upgrade Script 


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
<td><p>createGeneralJournalEntry_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies the country specific fields from the GeneralJournalEntry table to the GeneralJournalEntry_W table.</p></td>
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
<td><p>GeneralJournalEntry_W</p></td>
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
<td><p>GeneralJournalEntry_W</p></td>
<td><p>LedgerVoucherType_CN</p></td>
<td><p>LedgerVoucherTypeRefRecId_CN</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalEntry_W</p></td>
<td><p>Reversed_CN</p></td>
<td><p>NoYes</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalEntry_W</p></td>
<td><p>Voucher_CN</p></td>
<td><p>Voucher_CN</p></td>
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
<td><p>GeneralJournalEntry</p></td>
<td><p>LedgerVoucherType_CN</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalEntry</p></td>
<td><p>Reversed_CN</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalEntry</p></td>
<td><p>Voucher_CN</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

