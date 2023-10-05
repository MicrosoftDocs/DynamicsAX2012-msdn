---
title: ReleaseUpdateDB60_Ledger.createLedgerJournalTable_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.createLedgerJournalTable_W Upgrade Script
ms:assetid: 61d902e7-be95-8e38-405f-990ae95e8dbc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719106(v=AX.60)
ms:contentKeyID: 49708645
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.createLedgerJournalTable\_W Upgrade Script 


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
<td><p>createLedgerJournalTable_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country/region specific fields from &lt;c&gt;LedgerJournalTable&lt;/c&gt; table to &lt;c&gt;LedgerJournalTable_W&lt;/c&gt; table</p></td>
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
<td><p>LedgerJournalTable_W</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTable</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerJournalTable</p></th>
<th><p>To Table: LedgerJournalTable_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ApprovalStatus_CN</p></td>
<td><p>ApprovalStatus_CN</p></td>
</tr>
<tr class="even">
<td><p>CashAccount_W</p></td>
<td><p>CashAccount_W</p></td>
</tr>
<tr class="odd">
<td><p>DebitCurrencyCode_LT</p></td>
<td><p>DebitCurrencyCode_LT</p></td>
</tr>
<tr class="even">
<td><p>ForeignBankFee_LT</p></td>
<td><p>ForeignBankFee_LT</p></td>
</tr>
<tr class="odd">
<td><p>InformByPhone_LT</p></td>
<td><p>InformByPhone_LT</p></td>
</tr>
<tr class="even">
<td><p>InformByTelex_LT</p></td>
<td><p>InformByTelex_LT</p></td>
</tr>
<tr class="odd">
<td><p>PaymentPriority_LT</p></td>
<td><p>PaymentPriority_LT</p></td>
</tr>
<tr class="even">
<td><p>Prepayment_W</p></td>
<td><p>Prepayment_W</p></td>
</tr>
<tr class="odd">
<td><p>ReportPeriod_RU</p></td>
<td><p>ReportPeriod_RU</p></td>
</tr>
<tr class="even">
<td><p>Reverse_RU</p></td>
<td><p>Reverse_RU</p></td>
</tr>
<tr class="odd">
<td><p>ReverseType_RU</p></td>
<td><p>ReverseType_RU</p></td>
</tr>
</tbody>
</table>

  


