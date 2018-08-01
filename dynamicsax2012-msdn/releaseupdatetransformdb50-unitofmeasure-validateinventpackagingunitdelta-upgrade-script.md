---
title: ReleaseUpdateTransformDB50_UnitOfMeasure.validateInventPackagingUnitDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_UnitOfMeasure.validateInventPackagingUnitDelta Upgrade Script
ms:assetid: 50563e6c-f16c-75a8-c067-e1b8e184b665
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685519(v=AX.60)
ms:contentKeyID: 49708223
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_UnitOfMeasure.validateInventPackagingUnitDelta Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_UnitOfMeasure</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validateInventPackagingUnitDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates that there will be no unique index violations because of potential units merging in the InventPackagingUnit and InventPackagingUnitMaterial tables.</p></td>
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
<td><p>InventPackagingUnitMaterial</p></td>
</tr>
<tr class="even">
<td><p>InventPackagingUnit</p></td>
</tr>
</tbody>
</table>

  


