---
title: ReleaseUpdateDB60_Asset.updateAssetTableLV Upgrade Script
TOCTitle: ReleaseUpdateDB60_Asset.updateAssetTableLV Upgrade Script
ms:assetid: 92b380f5-9588-d7d6-984a-8d427834f200
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686101(v=AX.60)
ms:contentKeyID: 49709806
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Asset.updateAssetTableLV Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateAssetTableLV</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the DefaultDimension field of the AssetTable table with the corresponding value from the RecId field of the DimensionAttributeValueSet table.</p></td>
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
<td><p>AssetTable</p></td>
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
<th><p>From Table: AssetTable</p></th>
<th><p>To Table: AssetTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Del_Dimension_LV</p></td>
<td><p>DefaultDimension</p></td>
</tr>
</tbody>
</table>

  


