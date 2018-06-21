---
title: ReleaseUpdateDB60_Ledger.updateLedgerAllocationBasisRuleSource Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerAllocationBasisRuleSource Upgrade Script
ms:assetid: af935eb4-59d7-32ed-7c51-1023aebbef0a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686583(v=AX.60)
ms:contentKeyID: 49710538
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerAllocationBasisRuleSource Upgrade Script [AX 2012]


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
<td><p>updateLedgerAllocationBasisRuleSource</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts data from a single LedgerAllocationBasisRuleSource record to multiple records by transforming data from the BasisAccount and BasisDimension fields to the BasisCriteria field.</p></td>
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
<td><p>LedgerAllocationBasisRuleSource</p></td>
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
<th><p>From Table: LedgerAllocationBasisRuleSource</p></th>
<th><p>To Table: LedgerAllocationBasisRuleSource</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BasisAccount</p></td>
<td><p>BasisCriteria</p></td>
</tr>
<tr class="even">
<td><p>BasisDimension</p></td>
<td><p>BasisCriteria</p></td>
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
<td><p>LedgerAllocationBasisRuleSource</p></td>
<td><p>BasisCriteria</p></td>
<td><p>DimensionAccountCriteria</p></td>
</tr>
<tr class="even">
<td><p>LedgerAllocationBasisRuleSource</p></td>
<td><p>BasisDimensionAttribute</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>LedgerAllocationBasisRuleSource</p></td>
<td><p>FieldSetting</p></td>
<td><p>LedgerAllocationAccountDimension</p></td>
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
<td><p>LedgerAllocationBasisRuleSource</p></td>
<td><p>BasisAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerAllocationBasisRuleSource</p></td>
<td><p>BasisDimension</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

