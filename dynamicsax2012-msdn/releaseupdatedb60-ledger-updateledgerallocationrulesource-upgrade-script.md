---
title: ReleaseUpdateDB60_Ledger.updateLedgerAllocationRuleSource Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerAllocationRuleSource Upgrade Script
ms:assetid: aceb543a-60f5-caee-94e5-4c1006085073
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686513(v=AX.60)
ms:contentKeyID: 49710468
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerAllocationRuleSource Upgrade Script 


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
<td><p>updateLedgerAllocationRuleSource</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the DimensionCode field to the SourceDimensionAttribute field on the LedgerAllocationRuleSource table.</p></td>
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
<td><p>LedgerAllocationRuleSource</p></td>
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
<th><p>From Table: LedgerAllocationRuleSource</p></th>
<th><p>To Table: LedgerAllocationRuleSource</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DimensionCode</p></td>
<td><p>SourceDimensionAttribute</p></td>
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
<td><p>LedgerAllocationRuleSource</p></td>
<td><p>SourceDimensionAttribute</p></td>
<td><p>RefRecId</p></td>
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
<td><p>LedgerAllocationRuleSource</p></td>
<td><p>DimensionCode</p></td>
</tr>
</tbody>
</table>

  


