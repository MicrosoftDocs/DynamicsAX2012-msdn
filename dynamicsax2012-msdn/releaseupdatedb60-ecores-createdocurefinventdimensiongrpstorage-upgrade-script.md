﻿---
title: ReleaseUpdateDB60_EcoRes.createDocuRefInventDimensionGrpStorage Upgrade Script
TOCTitle: ReleaseUpdateDB60_EcoRes.createDocuRefInventDimensionGrpStorage Upgrade Script
ms:assetid: 7a9831c3-777d-e994-5da5-c824b5c46bd5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719418(v=AX.60)
ms:contentKeyID: 49709209
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createDocuRefInventDimensionGrpStorage Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_EcoRes</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createDocuRefInventDimensionGrpStorage</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates records in the DocuRef table that are related to the InventDimGroup and InventDimSetup tables. The records will be created to relate to the EcoResStorageDimensionGroup and EcoResStorageDimensionGroupFldSetup records.</p></td>
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
<td><p>Product management</p></td>
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
<td><p>DocuRef</p></td>
</tr>
<tr class="even">
<td><p>DEL_InventDimSetup</p></td>
</tr>
<tr class="odd">
<td><p>DEL_EcoResDimGroupUpgrade</p></td>
</tr>
<tr class="even">
<td><p>EcoResStorageDimensionGroup</p></td>
</tr>
<tr class="odd">
<td><p>EcoResStorageDimensionGroupFldSetup</p></td>
</tr>
</tbody>
</table>

  

