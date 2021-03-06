﻿---
title: ReleaseUpdateTransformDB40_EcoResProduct.validateItemCombinations Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_EcoResProduct.validateItemCombinations Upgrade Script
ms:assetid: b3805f97-15d8-8fc3-a1e6-bac19628234c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736938(v=AX.60)
ms:contentKeyID: 49710622
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_EcoResProduct.validateItemCombinations Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_EcoResProduct</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateItemCombinations</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates that all items that have item combinations have at least one item dimension active.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>inventtable</p></td>
</tr>
<tr class="even">
<td><p>InventDimCombination</p></td>
</tr>
<tr class="odd">
<td><p>InventDimSetup</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a validation script.

  


