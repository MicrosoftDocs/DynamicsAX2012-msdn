---
title: ReleaseUpdateTransformDB50_LedgerTrx.taxTransGeneralJournalAcctEntryToa Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_LedgerTrx.taxTransGeneralJournalAcctEntryToa Upgrade Script
ms:assetid: df5fdaab-ea89-1459-611f-1a0f3d848559
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737251(v=AX.60)
ms:contentKeyID: 49711693
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_LedgerTrx.taxTransGeneralJournalAcctEntryToa Upgrade Script 


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
<td><p>taxTransGeneralJournalAcctEntryToa</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the live pre-processing population of records in the TaxTransGeneralJournalAccountEntry table based on existing records in the LedgerTrans and TaxTrans tables for the TaxOffsetAccountUseTax.</p></td>
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

This is a helper method that is called by the main live preprocessing script and delta script for the TaxTrans table. The TaxTransGeneralJournalAccountEntry table will contain one record for every record in the TaxTrans table which has a value for the TaxOffsetAccountUseTax.

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
<td><p>TaxOffsetAccountUseTax/Dimension</p></td>
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

  


