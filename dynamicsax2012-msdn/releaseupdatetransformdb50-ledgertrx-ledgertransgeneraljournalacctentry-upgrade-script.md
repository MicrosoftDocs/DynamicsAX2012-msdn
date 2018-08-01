---
title: ReleaseUpdateTransformDB50_LedgerTrx.ledgerTransGeneralJournalAcctEntry Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_LedgerTrx.ledgerTransGeneralJournalAcctEntry Upgrade Script
ms:assetid: b9fa9b17-0070-8d25-3a3d-56f0b3ca1e70
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737110(v=AX.60)
ms:contentKeyID: 49710792
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_LedgerTrx.ledgerTransGeneralJournalAcctEntry Upgrade Script 


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
<td><p>ledgerTransGeneralJournalAcctEntry</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the live pre-processing population of records in the GeneralJournalAccountEntry table based on existing records in the LedgerTrans table.</p></td>
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
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a helper method called by the main live preprocessing script and delta script for the LedgerTrans table. The GeneralJournalAccountEntry table will contain one record for every record found in the LedgerTrans table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerTrans</p></th>
<th><p>To Table: GeneralJournalAccountEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AllocateLevel</p></td>
<td><p>AllocationLevel</p></td>
</tr>
<tr class="even">
<td><p>Correct</p></td>
<td><p>IsCorrection</p></td>
</tr>
<tr class="odd">
<td><p>Crediting</p></td>
<td><p>IsCredit</p></td>
</tr>
<tr class="even">
<td><p>DocumentDate</p></td>
<td><p>DocumentDate</p></td>
</tr>
<tr class="odd">
<td><p>DocumentNum</p></td>
<td><p>DocumentNumber</p></td>
</tr>
<tr class="even">
<td><p>AmountMST</p></td>
<td><p>FunctionalCurrencyAmount</p></td>
</tr>
<tr class="odd">
<td><p>PaymReference</p></td>
<td><p>PaymentReference</p></td>
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
<td><p>TransType</p></td>
<td><p>TransactionType</p></td>
</tr>
<tr class="odd">
<td><p>Posting</p></td>
<td><p>PostingType</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>DEL_LedgerTransRefRecId</p></td>
</tr>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>DEL_DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>AccountNum/Dimension</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>AmountMSTSecond</p></td>
<td><p>ReportingCurrencyAmount</p></td>
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
<th><p>From Table: GeneralJournalEntry</p></th>
<th><p>To Table: GeneralJournalAccountEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>GeneralJournalEntry</p></td>
</tr>
</tbody>
</table>

  


