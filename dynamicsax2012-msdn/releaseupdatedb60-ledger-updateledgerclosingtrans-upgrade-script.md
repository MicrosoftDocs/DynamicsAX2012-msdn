---
title: ReleaseUpdateDB60_Ledger.updateLedgerClosingTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerClosingTrans Upgrade Script
ms:assetid: 33d4bc1a-13f8-45b8-a23c-7a56779088f1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685112(v=AX.60)
ms:contentKeyID: 49707565
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerClosingTrans Upgrade Script 


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
<td><p>updateLedgerClosingTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the AccountNum and the Dimension fields to the LedgerDimension field and from the OffsetAccount and Dimension fields to the OffsetLedgerDimension field in the LedgerClosingTrans table.</p></td>
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
<td><p>LedgerClosingTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account or dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerClosingTrans</p></th>
<th><p>To Table: LedgerClosingTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountNum, Dimension</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>OffsetAccountNum, Dimension</p></td>
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
<td><p>LedgerClosingTrans</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerClosingTrans</p></td>
<td><p>OffsetLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
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
<td><p>LedgerClosingTrans</p></td>
<td><p>AccountNum</p></td>
</tr>
<tr class="even">
<td><p>LedgerClosingTrans</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="odd">
<td><p>LedgerClosingTrans</p></td>
<td><p>OffsetAccountNum</p></td>
</tr>
</tbody>
</table>

  


