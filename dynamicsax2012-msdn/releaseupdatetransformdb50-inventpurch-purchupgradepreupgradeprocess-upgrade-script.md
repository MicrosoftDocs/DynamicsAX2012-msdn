---
title: ReleaseUpdateTransformDB50_InventPurch.purchUpgradePreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_InventPurch.purchUpgradePreUpgradeProcess Upgrade Script
ms:assetid: 01b68caa-1caf-7301-1449-9a0ad994220f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684631(v=AX.60)
ms:contentKeyID: 49706328
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_InventPurch.purchUpgradePreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_InventPurch</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>purchUpgradePreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The pre-upgrade script, which creates account entries for packing slip relief.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Pre-processing60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>5.0</p></td>
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
<td><p>Cost accounting</p></td>
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
<td><p>DEL_InventPurchUpgradeAccountEntries</p></td>
</tr>
<tr class="even">
<td><p>InventTrans</p></td>
</tr>
<tr class="odd">
<td><p>InventTransPosting</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
</tr>
</tbody>
</table>

  


