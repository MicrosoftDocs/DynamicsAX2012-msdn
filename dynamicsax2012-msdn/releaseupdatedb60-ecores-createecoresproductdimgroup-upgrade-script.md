---
title: ReleaseUpdateDB60_EcoRes.createEcoResProductDimGroup Upgrade Script
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResProductDimGroup Upgrade Script
ms:assetid: d5df28f6-7959-17c8-9716-3ebc337b4dd7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687054(v=AX.60)
ms:contentKeyID: 49711502
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResProductDimGroup Upgrade Script 


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
<td><p>createEcoResProductDimGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new records in the EcoResProductDimensionGroup table. The data is created based on existing data in the InventDimSGroup table. The criteria used for determining how the dimension groups are updated are specified by the user during the pre-upgrade process.</p></td>
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
<td><p>EcoResProductDimensionGroup</p></td>
</tr>
<tr class="even">
<td><p>EcoResProductDimensionGroupFldSetup</p></td>
</tr>
<tr class="odd">
<td><p>DEL_EcoResProductDimensionGroupUpgrade</p></td>
</tr>
<tr class="even">
<td><p>DEL_EcoResProductDimensionGroupFldSetup</p></td>
</tr>
<tr class="odd">
<td><p>DEL_InventDimGroup</p></td>
</tr>
<tr class="even">
<td><p>DEL_InventDimSetup</p></td>
</tr>
<tr class="odd">
<td><p>InventTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The data on which the upgrade is dependent must be provided before the upgrade.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

