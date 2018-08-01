---
title: PmfReleaseUpdateTransformDB40.updateCWBOM Upgrade Script
TOCTitle: PmfReleaseUpdateTransformDB40.updateCWBOM Upgrade Script
ms:assetid: 34ace3bf-53d3-b960-0cf6-53c611202632
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685133(v=AX.60)
ms:contentKeyID: 49707586
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# PmfReleaseUpdateTransformDB40.updateCWBOM Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>PmfReleaseUpdateTransformDB40</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCWBOM</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the catch weight field and handles the renamed fields in the BOM table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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
<td><p>Process Distribution</p></td>
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
<td><p>BOM</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: BOM</p></th>
<th><p>New Table Name: BOM</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>PdsPackQty</p></td>
<td><p>PdsCWQty</p></td>
</tr>
<tr class="odd">
<td><p>PdsPackUnit</p></td>
<td><p>PdsCWUnitId</p></td>
</tr>
</tbody>
</table>

  


