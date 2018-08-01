---
title: ReleaseUpdateTransformDB40_Ledger.dimensionHierarchyPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.dimensionHierarchyPreProcessing Upgrade Script
ms:assetid: a3bdda7d-ed89-f5f5-e454-8a7189c6b373
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736765(v=AX.60)
ms:contentKeyID: 49710197
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.dimensionHierarchyPreProcessing Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>dimensionHierarchyPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the DimensionHierarchy records that will be used by the upgrade.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>DimensionHierarchy</p></td>
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
<td><p>DimensionHierarchy</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DimensionHierarchyLevel</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>DimensionConstraintTree</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DimensionConstraintNode</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>DimensionConstraintNodeCriteria</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


