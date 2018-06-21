---
title: ReleaseUpdateDB62_Products.updateProductMasterDimValueTranslation Upgrade Script
TOCTitle: ReleaseUpdateDB62_Products.updateProductMasterDimValueTranslation Upgrade Script
ms:assetid: 104201fa-0ee1-449b-38ad-bfbbde8a2e31
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn975035(v=AX.60)
ms:contentKeyID: 65236149
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Products.updateProductMasterDimValueTranslation Upgrade Script [AX 2012]


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
<td><p>updateProductMasterDimValueTranslation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates product master dimension value translations in the Product Information Management module.</p></td>
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

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

