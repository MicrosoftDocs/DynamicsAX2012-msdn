---
title: ReleaseUpdateTransformDB40_Ledger.ledgerTransDeltaPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.ledgerTransDeltaPreProcessing Upgrade Script
ms:assetid: 815ddbd3-fbc2-3f03-9c60-2be35038f431
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685919(v=AX.60)
ms:contentKeyID: 49709372
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.ledgerTransDeltaPreProcessing Upgrade Script 


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
<td><p>ledgerTransDeltaPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates and calls the stored procedures for the transformation of the LedgerTrans table to the GeneralJournalHeader, LedgerEntryJournal, LedgerEntryReference, GeneralJournalLine, LedgerEntry, and LedgerEntryJournalizing tables for any changes from the upgrade.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p>
<p>Preprocessing 60: Single user</p></td>
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
<td><p>GeneralJournalHeader</p></td>
</tr>
<tr class="odd">
<td><p>LedgerEntryJournal</p></td>
</tr>
<tr class="even">
<td><p>LedgerEntryReference</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalLine</p></td>
</tr>
<tr class="even">
<td><p>LedgerEntry</p></td>
</tr>
<tr class="odd">
<td><p>LedgerEntryJournalizing</p></td>
</tr>
</tbody>
</table>


## Remarks

This method calls various other methods that perform the actual transformations.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerTrans</p></th>
<th><p>To Table: GeneralJournalHeader</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(GeneratedValue)</p></td>
<td><p>LedgerCategory</p></td>
</tr>
<tr class="even">
<td><p>(GeneratedValue)</p></td>
<td><p>LegalEntity</p></td>
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
<th><p>To Table: LedgerEntryJournal</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JournalNum</p></td>
<td><p>JournalNumber</p></td>
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
<th><p>To Table: LedgerEntryReference</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(GeneratedValue)</p></td>
<td><p>LedgerEntryJournal</p></td>
</tr>
<tr class="even">
<td><p>Voucher</p></td>
<td><p>ReferenceNumber</p></td>
</tr>
<tr class="odd">
<td><p>TransDate</p></td>
<td><p>AccountingDate</p></td>
</tr>
<tr class="even">
<td><p>AcknowledgementDate</p></td>
<td><p>AcknowledgementDate</p></td>
</tr>
<tr class="odd">
<td><p>LedgerPostingJournalID</p></td>
<td><p>LedgerPostingJournal</p></td>
</tr>
<tr class="even">
<td><p>PeriodCode</p></td>
<td><p>PeriodCode</p></td>
</tr>
<tr class="odd">
<td><p>JournalNum</p></td>
<td><p>JournalNumber</p></td>
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
<th><p>To Table: GeneralJournalLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(GeneratedValue)</p></td>
<td><p>GeneralJournalHeader</p></td>
</tr>
<tr class="even">
<td><p>RecID</p></td>
<td><p>LedgerTrans</p></td>
</tr>
<tr class="odd">
<td><p>(GeneratedValue)</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AllocateLevel</p></td>
<td><p>AllocationLevel</p></td>
</tr>
<tr class="odd">
<td><p>Correct</p></td>
<td><p>IsCorrection</p></td>
</tr>
<tr class="even">
<td><p>Crediting</p></td>
<td><p>IsCredit</p></td>
</tr>
<tr class="odd">
<td><p>DocumentDate</p></td>
<td><p>DocumentDate</p></td>
</tr>
<tr class="even">
<td><p>DocumentNum</p></td>
<td><p>DocumentNumber</p></td>
</tr>
<tr class="odd">
<td><p>AmountMST</p></td>
<td><p>FunctionalCurrencyAmount</p></td>
</tr>
<tr class="even">
<td><p>PaymReference</p></td>
<td><p>PaymentReference</p></td>
</tr>
<tr class="odd">
<td><p>AmountMSTSecond</p></td>
<td><p>SecondaryCurrencyAmount</p></td>
</tr>
<tr class="even">
<td><p>AmountCur</p></td>
<td><p>TransactionCurrencyAmount</p></td>
</tr>
<tr class="odd">
<td><p>CurrencyCode</p></td>
<td><p>TransactionCurrencyCode</p></td>
</tr>
<tr class="even">
<td><p>DataAreaID</p></td>
<td><p>TransactionCurrencyDataAreaID</p></td>
</tr>
<tr class="odd">
<td><p>TransType</p></td>
<td><p>TransactionType</p></td>
</tr>
<tr class="even">
<td><p>Qty</p></td>
<td><p>Quantity</p></td>
</tr>
<tr class="odd">
<td><p>Posting</p></td>
<td><p>PostingType</p></td>
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
<th><p>To Table: LedgerEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(GeneratedValue)</p></td>
<td><p>LedgerEntryReference</p></td>
</tr>
<tr class="even">
<td><p>(GeneratedValue)</p></td>
<td><p>GeneralJournalLine</p></td>
</tr>
<tr class="odd">
<td><p>CompanyBankAccountID</p></td>
<td><p>CompanyBankAccount</p></td>
</tr>
<tr class="even">
<td><p>FurtherPostingType</p></td>
<td><p>LedgerTransFurtherPosting</p></td>
</tr>
<tr class="odd">
<td><p>PayMode</p></td>
<td><p>PaymentMode</p></td>
</tr>
<tr class="even">
<td><p>Qty</p></td>
<td><p>Quantity</p></td>
</tr>
<tr class="odd">
<td><p>ThirdPartyBankAccountID</p></td>
<td><p>ThirdPartyBankAccount</p></td>
</tr>
<tr class="even">
<td><p>Txt</p></td>
<td><p>Text</p></td>
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
<td><p>(GeneratedValue)</p></td>
<td><p>LedgerEntry</p></td>
</tr>
</tbody>
</table>

  


