---
title: ReleaseUpdateTransformDB50_FimDimGroup.inventTransPostingPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_FimDimGroup.inventTransPostingPreUpgradeProcess Upgrade Script
ms:assetid: bd0ed3c7-018c-2bf5-297e-b444257bdf7d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686686(v=AX.60)
ms:contentKeyID: 49710884
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_FimDimGroup.inventTransPostingPreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_FimDimGroup</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>inventTransPostingPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the Account and Dimension fields to the LedgerDimension field and from the OffsetAccount and Dimension fields to the OffsetLedgerDimension field in the InventTransPosting table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>InventTransPosting</p></td>
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
<th><p>From Table: InventTransPosting</p></th>
<th><p>To Table: InventTransPosting</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Account, Dimension</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AccountOffset, Dimension</p></td>
<td><p>OffsetLedgerDimension</p></td>
</tr>
<tr class="odd">
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
<td><p>InventTransPosting</p></td>
<td><p>OffsetLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="even">
<td><p>InventTransPosting</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="odd">
<td><p>InventTransPosting</p></td>
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
<td><p>InventTransPosting</p></td>
<td><p>Account</p></td>
</tr>
<tr class="even">
<td><p>InventTransPosting</p></td>
<td><p>AccountOffset</p></td>
</tr>
<tr class="odd">
<td><p>InventTransPosting</p></td>
<td><p>Dimension</p></td>
</tr>
</tbody>
</table>

  


