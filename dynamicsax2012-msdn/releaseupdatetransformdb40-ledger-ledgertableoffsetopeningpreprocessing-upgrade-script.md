---
title: ReleaseUpdateTransformDB40_Ledger.ledgerTableOffsetOpeningPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.ledgerTableOffsetOpeningPreProcessing Upgrade Script
ms:assetid: 23ceaa55-1a0a-7e4a-9873-574727869b2c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684979(v=AX.60)
ms:contentKeyID: 49707182
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.ledgerTableOffsetOpeningPreProcessing Upgrade Script 


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
<td><p>ledgerTableOffsetOpeningPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts the OffsetAccount and OpeningAccount fields in the LedgerTable table to the dimensions fields in the MainAccount table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
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
<td><p>MainAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to convert the account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerTable</p></th>
<th><p>To Table: MainAccount</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OffsetAccount</p></td>
<td><p>OffsetLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>OpeningAccount</p></td>
<td><p>OpeningAccount</p></td>
</tr>
</tbody>
</table>

  


