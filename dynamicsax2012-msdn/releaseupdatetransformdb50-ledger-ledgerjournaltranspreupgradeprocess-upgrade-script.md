---
title: ReleaseUpdateTransformDB50_Ledger.ledgerJournalTransPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.ledgerJournalTransPreUpgradeProcess Upgrade Script
ms:assetid: c6b63712-5982-de6d-112d-2b75e6bb861d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719551(v=AX.60)
ms:contentKeyID: 49711119
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.ledgerJournalTransPreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerJournalTransPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from fields that hold the account and dimension data to the fields that hold the new accounts and dimension model in Microsoft Dynamics AX 2012.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
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
<td><p>LedgerJournalTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerJournalTrans</p></th>
<th><p>To Table: Shadow_LedgerJournalTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
<tr class="even">
<td><p>AccountNum</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>OffsetDefaultDimension</p></td>
</tr>
<tr class="even">
<td><p>OffsetAccount, InterCoDimension</p></td>
<td><p>OffsetLedgerDimension</p></td>
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
<td><p>LedgerJournalTrans</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
<td><p>LedgerDimension</p></td>
<td><p>DimensionDynamicAccount</p></td>
</tr>
<tr class="odd">
<td><p>LedgerJournalTrans</p></td>
<td><p>OffsetDefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
<td><p>OffsetLedgerDimension</p></td>
<td><p>DimensionDynamicAccount</p></td>
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
<td><p>Dimension</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
<td><p>AccountNum</p></td>
</tr>
<tr class="odd">
<td><p>LedgerJournalTrans</p></td>
<td><p>OffsetAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
<td><p>InterCoDimension</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

