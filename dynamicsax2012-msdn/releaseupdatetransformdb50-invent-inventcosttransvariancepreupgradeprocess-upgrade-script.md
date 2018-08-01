---
title: ReleaseUpdateTransformDB50_Invent.inventCostTransVariancePreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Invent.inventCostTransVariancePreUpgradeProcess Upgrade Script
ms:assetid: 3ed1d682-6454-c0cc-0df1-adcd02ebda4d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718771(v=AX.60)
ms:contentKeyID: 49707826
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Invent.inventCostTransVariancePreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>inventCostTransVariancePreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms account and dimension data for the InventCostTransVariance table.</p></td>
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
<td><p>InventCostTransVariance</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is used to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: InventCostTransVariance</p></th>
<th><p>To Table: InventCostTransVariance</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
<tr class="even">
<td><p>Account</p></td>
<td><p>LedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>AccountOffset</p></td>
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
<td><p>InventCostTransVariance</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
<tr class="even">
<td><p>InventCostTransVariance</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="odd">
<td><p>InventCostTransVariance</p></td>
<td><p>OffsetLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
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
<td><p>InventCostTransVariance</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="even">
<td><p>InventCostTransVariance</p></td>
<td><p>Account</p></td>
</tr>
<tr class="odd">
<td><p>InventCostTransVariance</p></td>
<td><p>AccountOffset</p></td>
</tr>
</tbody>
</table>

  


