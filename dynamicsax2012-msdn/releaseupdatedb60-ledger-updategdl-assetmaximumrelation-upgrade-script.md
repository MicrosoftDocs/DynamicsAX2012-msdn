---
title: ReleaseUpdateDB60_Ledger.updateGDL_AssetMaximumRelation Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_AssetMaximumRelation Upgrade Script
ms:assetid: dcc67462-f295-3f1c-6b5a-71def210e024
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737223(v=AX.60)
ms:contentKeyID: 49711666
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_AssetMaximumRelation Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>Updates the MaxRelationRBFactor column with the value stored in the DEL_MaxRelationRB_SL of the AssetParametersDeprRates_DE table.</p></td>
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

The MaxRelationRB\_SL column allows only integer values. However, due to a new requirement, the relation value can be a real value. A new real-based MaxRelationRBFactor column is created to store the relation values.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

