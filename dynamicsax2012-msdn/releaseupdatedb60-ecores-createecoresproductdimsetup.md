---
title: ReleaseUpdateDB60_EcoRes.createEcoResProductDimSetup
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResProductDimSetup
ms:assetid: b40525ec-ebbe-d3ac-8c1d-bcb5f7396d35
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736961(v=AX.60)
ms:contentKeyID: 49710645
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResProductDimSetup 


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
<td><p>createEcoResProductDimSetup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new records in the &lt;c&gt;EcoResProductDimensionGroupFldSetup&lt;/c&gt; table. The data is created based on existing data in the &lt;c&gt;InventDimSetup&lt;/c&gt; table. The criterias used for determining how the dimension field setups are updated, are specified by the user during the pre-upgrade process.</p></td>
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
<td><p>DEL_EcoResProductDimensionGroupFldSetup</p></td>
</tr>
<tr class="even">
<td><p>DEL_InventDimSetup</p></td>
</tr>
</tbody>
</table>


## Remarks

The data that the upgrade is dependent on must be provided before upgrade.

  


