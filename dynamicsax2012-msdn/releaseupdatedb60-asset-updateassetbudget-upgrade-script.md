﻿---
title: ReleaseUpdateDB60_Asset.updateAssetBudget Upgrade Script
TOCTitle: ReleaseUpdateDB60_Asset.updateAssetBudget Upgrade Script
ms:assetid: 4d599b7b-3e5d-ce52-7af2-96ddf5ca19d1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685438(v=AX.60)
ms:contentKeyID: 49708144
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Asset.updateAssetBudget Upgrade Script 


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
<td><p>updateAssetBudget</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the LedgerAccount and the Dimension field to the LedgerDimension field and the LedgerAccountOffset and the Dimension fields to the OffsetLedgerDimension field in the AssetBudget table.</p></td>
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
<td><p>AssetBudget</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AssetBudget</p></th>
<th><p>To Table: AssetBudget</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LedgerAccount, Dimension</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>LedgerAccountOffset, Dimension</p></td>
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
<td><p>AssetBudget</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>AssetBudget</p></td>
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
<td><p>AssetBudget</p></td>
<td><p>LedgerAccount</p></td>
</tr>
<tr class="even">
<td><p>AssetBudget</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="odd">
<td><p>AssetBudget</p></td>
<td><p>LedgerAccountOffset</p></td>
</tr>
</tbody>
</table>

  


