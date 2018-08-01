---
title: ReleaseUpdateDB60_Ledger.updateGDL_AssetMaximumRelation
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_AssetMaximumRelation
ms:assetid: 1b21d9f5-dc78-16ad-ed0d-0b1c05eb4314
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718670(v=AX.60)
ms:contentKeyID: 49706953
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_AssetMaximumRelation 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateGDL_AssetMaximumRelation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the MaxRelationRBFactor column with the value stored in DEL_MaxRelationRB_SL of table AssetParametersDeprRates_DE.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>AssetParametersDeprRates_DE</p></td>
</tr>
</tbody>
</table>


## Remarks

MaxRelationRB\_SL column allows only integer values, however, due to a new requirement relation value can be a real value. A new real based column MaxRelationRBFactor is created to store the relation values.

  


