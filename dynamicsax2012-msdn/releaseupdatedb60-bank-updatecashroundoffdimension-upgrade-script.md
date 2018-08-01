---
title: ReleaseUpdateDB60_Bank.updateCashRoundOffDimension Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.updateCashRoundOffDimension Upgrade Script
ms:assetid: 67ff046e-863d-de85-b0b7-fa479cf218c6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685598(v=AX.60)
ms:contentKeyID: 49708799
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.updateCashRoundOffDimension Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Bank</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCashRoundOffDimension</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the RoundOffLedgerDimension field of the RCashLedgerAccount table from the DEL_RoundOffAccount_HU field of the same table.</p></td>
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
<td><p>Bank</p></td>
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
<td><p>RCashLedgerAccount</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the new reference based dimension field with value from old ledger account based field.

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
<td><p>RCashLedgerAccount</p></td>
<td><p>RoundOffLedgerDimension</p></td>
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
<td><p>RCashLedgerAccount</p></td>
<td><p>DEL_RoundOffAccount_HU</p></td>
</tr>
</tbody>
</table>

  


