---
title: ReleaseUpdateTransformDB50_LedgerTrx.ledgerTransLedgerEntry Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_LedgerTrx.ledgerTransLedgerEntry Upgrade Script
ms:assetid: ddabec4b-36ff-3847-8067-2e4953744d80
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737216(v=AX.60)
ms:contentKeyID: 49711659
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_LedgerTrx.ledgerTransLedgerEntry Upgrade Script 


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
<td><p>ledgerTransLedgerEntry</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the live pre-processing population of records in the LedgerEntry table based upon the existing records in the LedgerTrans table.</p></td>
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
<td><p>LedgerEntry</p></td>
</tr>
<tr class="odd">
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a helper method that is called by the main live preprocessing script and the delta script for the LedgerTrans table. The LedgerEntry table will contain one record for every record that is found in the LedgerTrans table.

## Data Migration Section

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
<td><p>CompanyBankAccountId</p></td>
<td><p>CompanyBankAccount</p></td>
</tr>
<tr class="even">
<td><p>ThirdPartyBankAccountId</p></td>
<td><p>ThirdPartyBankAccount</p></td>
</tr>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>BankDataAreaId</p></td>
</tr>
<tr class="even">
<td><p>ConsolidatedCompany</p></td>
<td><p>ConsolidatedCompany</p></td>
</tr>
<tr class="odd">
<td><p>FurtherPostingType</p></td>
<td><p>IsBridgingPosting</p></td>
</tr>
<tr class="even">
<td><p>PaymMode</p></td>
<td><p>PaymentMode</p></td>
</tr>
<tr class="odd">
<td><p>ReasonRefRecId</p></td>
<td><p>ReasonRef</p></td>
</tr>
<tr class="even">
<td><p>Txt</p></td>
<td><p>Text</p></td>
</tr>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DEL_LedgerTransRefRecId</p></td>
</tr>
<tr class="even">
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
<th><p>From Table: GeneralJournalAccountEntry</p></th>
<th><p>To Table: LedgerEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
</tbody>
</table>

  


