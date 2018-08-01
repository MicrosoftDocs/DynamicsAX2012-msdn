---
title: ReleaseUpdateDB60_Basic.updateEmplAdvanceHoldersDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateEmplAdvanceHoldersDimensions_RU Upgrade Script
ms:assetid: 251fd431-dd0e-161c-d78b-fd6f6636352a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685008(v=AX.60)
ms:contentKeyID: 49707208
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateEmplAdvanceHoldersDimensions\_RU Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEmplAdvanceHoldersDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the LedgerAccountProfit and LedgerAccountLoss fields to the ProfitLedgerDimension and LossLedgerDimension fields in the EmplParameters_RU table</p></td>
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
<td><p>EmplParameters_RU</p></td>
</tr>
<tr class="even">
<td><p>EmplLedgerAccounts_RU</p></td>
</tr>
<tr class="odd">
<td><p>EmplGroup_RU</p></td>
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
<th><p>From Table: EmplParameters_RU</p></th>
<th><p>To Table: EmplParameters_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LedgerAccountProfit</p></td>
<td><p>ProfitLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>LedgerAccountLoss</p></td>
<td><p>LossLedgerDimension</p></td>
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
<th><p>From Table: EmplLedgerAccounts_RU</p></th>
<th><p>To Table: EmplLedgerAccounts_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SumAccount</p></td>
<td><p>SummaryLedgerDimension</p></td>
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
<th><p>From Table: EmplGroup_RU</p></th>
<th><p>To Table: EmplGroup_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OffsetLedgerAccount</p></td>
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
<td><p>EmplParameters_RU</p></td>
<td><p>ProfitLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>EmplParameters_RU</p></td>
<td><p>LossLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>EmplLedgerAccounts_RU</p></td>
<td><p>SummaryLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>EmplGroup_RU</p></td>
<td><p>OffsetLedgerDimension</p></td>
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
<td><p>EmplParameters_RU</p></td>
<td><p>LedgerAccountProfit</p></td>
</tr>
<tr class="even">
<td><p>EmplParameters_RU</p></td>
<td><p>LedgerAccountLoss</p></td>
</tr>
<tr class="odd">
<td><p>EmplLedgerAccounts_RU</p></td>
<td><p>SumAccount</p></td>
</tr>
<tr class="even">
<td><p>EmplGroup_RU</p></td>
<td><p>OffsetLedgerAccount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

