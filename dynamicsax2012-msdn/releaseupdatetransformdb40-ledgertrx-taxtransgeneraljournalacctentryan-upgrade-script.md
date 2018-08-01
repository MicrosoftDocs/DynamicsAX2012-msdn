---
title: ReleaseUpdateTransformDB40_LedgerTrx.taxTransGeneralJournalAcctEntryAn Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_LedgerTrx.taxTransGeneralJournalAcctEntryAn Upgrade Script
ms:assetid: 143c25e3-4cdd-fd97-3148-941aa6205e88
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718508(v=AX.60)
ms:contentKeyID: 49706793
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_LedgerTrx.taxTransGeneralJournalAcctEntryAn Upgrade Script 


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
<td><p>taxTransGeneralJournalAcctEntryAn</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the live pre-processing population of records in the TaxTransGeneralJournalAccountEntry table based upon existing records in the LedgerTrans and TaxTrans tables for the AccountNum.</p></td>
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
<td><p>TaxTrans</p></td>
</tr>
<tr class="even">
<td><p>LedgerTrans</p></td>
</tr>
<tr class="odd">
<td><p>TaxTransGeneralJournalAccountEntry</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a helper method called by the main live preprocessing script and delta script for the TaxTrans table. The TaxTransGeneralJournalAccountEntry table will contain one record for every record in the TaxTrans table which has a value for the AccountNum.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TaxTrans</p></th>
<th><p>To Table: TaxTransGeneralJournalAccountEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>TaxTrans</p></td>
</tr>
<tr class="even">
<td><p>TaxTransRelationshipType::Tax</p></td>
<td><p>TaxTransRelationship</p></td>
</tr>
<tr class="odd">
<td><p>AccountNum/Dimension</p></td>
<td><p>LedgerDimension</p></td>
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
<th><p>To Table: TaxTransGeneralJournalAccountEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
<tr class="even">
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimension</p></td>
</tr>
</tbody>
</table>

  


