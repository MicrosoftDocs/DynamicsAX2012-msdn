---
title: ReleaseUpdateDB62_Products.upgradeProductMasterDimValueTranslation Upgrade Script
TOCTitle: ReleaseUpdateDB62_Products.upgradeProductMasterDimValueTranslation Upgrade Script
ms:assetid: 48b56a2a-8f26-cce1-1acb-5fca1b2f9702
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702726(v=AX.60)
ms:contentKeyID: 65236182
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Products.upgradeProductMasterDimValueTranslation Upgrade Script 


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB62_Products</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>upgradeProductMasterDimValueTranslation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates translations of product master dimension values in the Product information management module.</p></td>
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
<td><p>ECORESPRODUCTMASTERDIMVALUETRANSLATION</p></td>
</tr>
<tr class="even">
<td><p>ECORESPRODUCTMASTERDIMENSIONVALUE</p></td>
</tr>
</tbody>
</table>


## Remarks

The names and descriptions of product master dimension values are moved to \<c\>ProductMasterDimValueTranslation\</c\> to enable translation.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EcoResProductMasterDimensionValue</p></th>
<th><p>To Table: EcoResProductMasterDimValueTranslation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Description</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>DEL_AdditionalDescription</p></td>
<td><p>Description</p></td>
</tr>
</tbody>
</table>

  


