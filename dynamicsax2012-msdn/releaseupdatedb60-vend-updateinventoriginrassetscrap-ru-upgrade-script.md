---
title: ReleaseUpdateDB60_Vend.updateInventOriginRAssetScrap_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateInventOriginRAssetScrap_RU Upgrade Script
ms:assetid: 7c51a4a6-5e45-2a80-acb3-9924c9d1e1cc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719472(v=AX.60)
ms:contentKeyID: 49709262
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateInventOriginRAssetScrap\_RU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateInventOriginRAssetScrap_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the InventTransOriginRAssetScrap_RU table with the relationship information from the RAssetScrap and InventTransOrigin tables.</p></td>
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
<tr class="even">
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
<td><p>InventTransOriginRAssetScrap_RU</p></td>
</tr>
<tr class="even">
<td><p>InventTransOriginRAssetScrap_RU</p></td>
</tr>
<tr class="odd">
<td><p>InventTransOriginRAssetScrap_RU</p></td>
</tr>
<tr class="even">
<td><p>InventTransOrigin</p></td>
</tr>
<tr class="odd">
<td><p>RAssetScrap</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: RAssetScrap</p></th>
<th><p>To Table: InventTransOriginRAssetScrap_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>RAssetScrap</p></td>
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
<th><p>From Table: InventTransOrigin</p></th>
<th><p>To Table: InventTransOriginRAssetScrap</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>InventTransOrigin</p></td>
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
<td><p>InventTransOriginRAssetScrap_RU</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


