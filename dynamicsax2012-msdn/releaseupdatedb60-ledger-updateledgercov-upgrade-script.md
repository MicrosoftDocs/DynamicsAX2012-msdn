---
title: ReleaseUpdateDB60_Ledger.updateLedgerCov Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerCov Upgrade Script
ms:assetid: ac299cd5-e205-5cd2-776c-747eb9af76d4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686487(v=AX.60)
ms:contentKeyID: 49710442
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerCov Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateLedgerCov</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Removes the LedgerCov records that are associated to ledger budget data. Also transforms data from the AccountNum and Dimension fields to the MainAccount and DefaultDimension fields in the LedgerLiquidity table.</p></td>
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
<td><p>LedgerCov</p></td>
</tr>
</tbody>
</table>


## Remarks

This method removes all records in the LedgerCov table that are associated to ledger budget data. These records have the TransTableId field set to the LedgerBudget table ID. Also, the transformation of fields is required in order to convert account or dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012. This method is to be run as a PostSync, Standard job.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerCov</p></th>
<th><p>To Table: LedgerCov</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountNum</p></td>
<td><p>MainAccount</p></td>
</tr>
<tr class="even">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
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
<td><p>LedgerCov</p></td>
<td><p>MainAccount</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>LedgerCov</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
</tbody>
</table>

  


