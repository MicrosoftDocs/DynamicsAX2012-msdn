---
title: ReleaseUpdateDB60_Asset.updateRAssetLedgerAccounts_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Asset.updateRAssetLedgerAccounts_RU Upgrade Script
ms:assetid: 1c079ee5-2104-f746-6625-9c1e76037d87
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718691(v=AX.60)
ms:contentKeyID: 49706974
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Asset.updateRAssetLedgerAccounts\_RU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Asset</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateRAssetLedgerAccounts_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the AssetLedgerAccount and AssetLedgerOffsetAccount fields to the AssetLedgerDimension and AssetOffsetLedgerDimension fields in the RAssetLedgerAccounts table</p></td>
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
<td><p>Fixed Asset</p></td>
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
<td><p>RAssetLedgerAccounts</p></td>
</tr>
<tr class="even">
<td><p>RAssetLedgerAccountsByLocation</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account/dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: RAssetLedgerAccounts</p></th>
<th><p>To Table: RAssetLedgerAccounts</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AssetLedgerAccount</p></td>
<td><p>AssetLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AssetLedgerOffsetAccount</p></td>
<td><p>AssetOffsetLedgerDimension</p></td>
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
<th><p>From Table: RAssetLedgerAccountsByLocation</p></th>
<th><p>To Table: RAssetLedgerAccountsByLocation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AssetLedgerAccount</p></td>
<td><p>AssetLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>LedgerAccountForDepreciationBonus</p></td>
<td><p>DepreciationBonusLedgerDimension</p></td>
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
<td><p>RAssetLedgerAccounts</p></td>
<td><p>AssetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>RAssetLedgerAccounts</p></td>
<td><p>AssetOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>RAssetLedgerAccountsByLocation</p></td>
<td><p>AssetLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>RAssetLedgerAccountsByLocation</p></td>
<td><p>DepreciationBonusLedgerDimension</p></td>
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
<td><p>RAssetLedgerAccounts</p></td>
<td><p>AssetLedgerAccount</p></td>
</tr>
<tr class="even">
<td><p>RAssetLedgerAccounts</p></td>
<td><p>AssetLedgerOffsetAccount</p></td>
</tr>
<tr class="odd">
<td><p>RAssetLedgerAccountsByLocation</p></td>
<td><p>AssetLedgerAccount</p></td>
</tr>
<tr class="even">
<td><p>RAssetLedgerAccountsByLocation</p></td>
<td><p>LedgerAccountForDepreciationBonus</p></td>
</tr>
</tbody>
</table>

  


