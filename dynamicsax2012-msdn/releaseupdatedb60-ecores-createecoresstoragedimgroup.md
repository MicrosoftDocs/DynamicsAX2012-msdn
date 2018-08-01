---
title: ReleaseUpdateDB60_EcoRes.createEcoResStorageDimGroup
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResStorageDimGroup
ms:assetid: edc72eeb-4b6a-e5fa-b5c5-a471623b7ca5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719949(v=AX.60)
ms:contentKeyID: 49712021
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResStorageDimGroup 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>createEcoResStorageDimGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new records in the &lt;c&gt;EcoResStorageDimensionGroup&lt;/c&gt; table. The data is created based on existing data in the &lt;c&gt;InventDimGroup&lt;/c&gt; table. The criterias used for determining how the dimension groups are updated, are specified by the user during the pre-upgrade process.</p></td>
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
<td><p>DEL_InventDimSetup</p></td>
</tr>
<tr class="even">
<td><p>DEL_EcoResDimGroupUpgrade</p></td>
</tr>
<tr class="odd">
<td><p>DEL_EcoResStorageDimGroupUpgrade</p></td>
</tr>
<tr class="even">
<td><p>EcoResStorageDimensionGroup</p></td>
</tr>
</tbody>
</table>


## Remarks

The data that the upgrade is dependent on must be provided before upgrade.

  


