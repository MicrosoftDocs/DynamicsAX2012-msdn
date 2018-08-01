---
title: ReleaseUpdateDB60_Ledger.updateLedgerEliminationRuleLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerEliminationRuleLine Upgrade Script
ms:assetid: c3e97398-c362-33ec-c042-2e7f685edcf8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686842(v=AX.60)
ms:contentKeyID: 49711039
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerEliminationRuleLine Upgrade Script 


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
<td><p>updateLedgerEliminationRuleLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the Account and Dimension fields to the LedgerDimension and the DefaultDimension fields in the LedgerEliminationRuleLines table.</p></td>
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
<td><p>LedgerEliminationRuleLines</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account/dimension data to the new accounts and dimension model for 6.0

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerEliminationRuleLines</p></th>
<th><p>To Table: LedgerEliminationRuleLines</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Account</p></td>
<td><p>LedgerDimension</p></td>
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
<td><p>LedgerEliminationRuleLines</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerEliminationRuleLines</p></td>
<td><p>DefaultDimension</p></td>
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
<td><p>LedgerEliminationRuleLines</p></td>
<td><p>Account</p></td>
</tr>
<tr class="even">
<td><p>LedgerEliminationRuleLines</p></td>
<td><p>Dimension</p></td>
</tr>
</tbody>
</table>

  


