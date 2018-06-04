---
title: ReleaseUpdateTransformDB40_LedgerTrx.ledgerTransGeneralJournalEntryInsert Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_LedgerTrx.ledgerTransGeneralJournalEntryInsert Upgrade Script
ms:assetid: 659af022-f878-a27b-9f0a-aca685b29e2e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719202(v=AX.60)
ms:contentKeyID: 49708741
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_LedgerTrx.ledgerTransGeneralJournalEntryInsert Upgrade Script 


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
<td><p>ledgerTransGeneralJournalEntryInsert</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Performs the live pre-processing population of records in the GeneralJournalEntry table based upon existing records in the LedgerTrans table.</p></td>
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
<tr class="odd">
<td><p>SubledgerVoucherGeneralJournalEntry</p></td>
</tr>
<tr class="even">
<td><p>Ledger</p></td>
</tr>
<tr class="odd">
<td><p>FiscalCalendarYear</p></td>
</tr>
<tr class="even">
<td><p>FiscalCalendarPeriod</p></td>
</tr>
</tbody>
</table>


## Remarks

This is an action method that is called by the helper method which handles the creation of the GeneralJournalEntry records.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerTrans</p></th>
<th><p>To Table: GeneralJournalEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JournalNum</p></td>
<td><p>DEL_JournalNumber</p></td>
</tr>
<tr class="even">
<td><p>TransDate</p></td>
<td><p>AccountingDate</p></td>
</tr>
<tr class="odd">
<td><p>LedgerPostingJournalId</p></td>
<td><p>LedgerPostingJournal</p></td>
</tr>
<tr class="even">
<td><p>PeriodCode</p></td>
<td><p>PeriodCode</p></td>
</tr>
<tr class="odd">
<td><p>OperationsTax</p></td>
<td><p>PostingLayer</p></td>
</tr>
<tr class="even">
<td><p>Voucher</p></td>
<td><p>DEL_Voucher</p></td>
</tr>
<tr class="odd">
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
<th><p>From Table: Ledger</p></th>
<th><p>To Table: GeneralJournalEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Ledger</p></td>
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
<th><p>From Table: FiscalCalendarYear</p></th>
<th><p>To Table: GeneralJournalEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalCalendarYear</p></td>
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
<th><p>From Table: FiscalCalendarPeriod</p></th>
<th><p>To Table: GeneralJournalEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalCalendarPeriod</p></td>
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
<th><p>From Table: LedgerTrans</p></th>
<th><p>To Table: SubledgerVoucherGeneralJournalEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TransDate</p></td>
<td><p>AccountingDate</p></td>
</tr>
<tr class="even">
<td><p>Voucher</p></td>
<td><p>Voucher</p></td>
</tr>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>VoucherDataAreaId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

