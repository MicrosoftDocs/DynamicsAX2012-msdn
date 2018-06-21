---
title: ReleaseUpdateTransformDB40_InventPurch.purchUpgradePreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_InventPurch.purchUpgradePreUpgradeProcess Upgrade Script
ms:assetid: b40ed49b-8003-ea15-edc6-aae1516431ad
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736952(v=AX.60)
ms:contentKeyID: 49710635
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_InventPurch.purchUpgradePreUpgradeProcess Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_InventPurch</p></td>
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
<td><p>4.01</p></td>
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

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

