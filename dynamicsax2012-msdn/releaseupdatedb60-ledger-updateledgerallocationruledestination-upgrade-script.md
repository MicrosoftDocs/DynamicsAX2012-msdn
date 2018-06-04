---
title: ReleaseUpdateDB60_Ledger.updateLedgerAllocationRuleDestination Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerAllocationRuleDestination Upgrade Script
ms:assetid: a12b112b-fe0e-606a-28a9-9d6f17ed0169
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736724(v=AX.60)
ms:contentKeyID: 49710156
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerAllocationRuleDestination Upgrade Script 


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
<td><p>updateLedgerAllocationRuleDestination</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the ToAccount and the ToDimension fields to the ToLedgerDimension and the ToDefaultDimension fields, respectively, in the LedgerAllocationRuleDestination table.</p></td>
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
<td><p>LedgerAllocationRuleDestination</p></td>
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
<th><p>From Table: LedgerAllocationRuleDestination</p></th>
<th><p>To Table: LedgerAllocationRuleDestination</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ToAccount</p></td>
<td><p>ToLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>ToDimension</p></td>
<td><p>ToDefaultDimension</p></td>
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
<td><p>LedgerAllocationRuleDestination</p></td>
<td><p>ToLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerAllocationRuleDestination</p></td>
<td><p>ToDefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
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
<td><p>LedgerAllocationRuleDestination</p></td>
<td><p>ToAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerAllocationRuleDestination</p></td>
<td><p>ToDimension</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

