---
title: ReleaseUpdateDB60_Basic.updateUnitOfMeasureTranslation Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateUnitOfMeasureTranslation Upgrade Script
ms:assetid: 99168557-48da-a9b7-e862-920f8c4c1d32
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686255(v=AX.60)
ms:contentKeyID: 49709958
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateUnitOfMeasureTranslation Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateUnitOfMeasureTranslation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the UnitOfMeasureTranslation table with the records created based on the DEL_Unit table data and the preupgrade data.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>DEL_Unit</p></td>
</tr>
<tr class="even">
<td><p>DEL_UnitUnitOfMeasureUpgrade</p></td>
</tr>
<tr class="odd">
<td><p>UnitOfMeasure</p></td>
</tr>
<tr class="even">
<td><p>GlobalParameters</p></td>
</tr>
<tr class="odd">
<td><p>UnitOfMeasureTranslation</p></td>
</tr>
</tbody>
</table>

  


