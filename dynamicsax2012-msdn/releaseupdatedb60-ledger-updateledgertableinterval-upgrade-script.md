---
title: ReleaseUpdateDB60_Ledger.updateLedgerTableInterval Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerTableInterval Upgrade Script
ms:assetid: 298218e6-bc4c-d70a-decd-88c4018c4e38
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735898(v=AX.60)
ms:contentKeyID: 49707315
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerTableInterval Upgrade Script 


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
<td><p>updateLedgerTableInterval</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the FromAccount and the ToAccount fields to the FromLedgerDimension and the ToLedgerDimension fields in the LedgerTableInterval table.</p></td>
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
<td><p>LedgerTableInterval</p></td>
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
<th><p>From Table: LedgerTableInterval</p></th>
<th><p>To Table: LedgerTableInterval</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FromAccount</p></td>
<td><p>FromLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>ToAccount</p></td>
<td><p>ToLedgerDimension</p></td>
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
<td><p>LedgerTableInterval</p></td>
<td><p>FromLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerTableInterval</p></td>
<td><p>ToLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
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
<td><p>LedgerTableInterval</p></td>
<td><p>FromAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerTableInterval</p></td>
<td><p>ToAccount</p></td>
</tr>
</tbody>
</table>

  


