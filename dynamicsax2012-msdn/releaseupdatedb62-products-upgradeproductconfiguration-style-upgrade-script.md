---
title: ReleaseUpdateDB62_Products.upgradeProductConfiguration_Style Upgrade Script
TOCTitle: ReleaseUpdateDB62_Products.upgradeProductConfiguration_Style Upgrade Script
ms:assetid: eff9c9c7-fd2e-7030-9c79-d78b3b757f06
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702832(v=AX.60)
ms:contentKeyID: 65236287
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Products.upgradeProductConfiguration\_Style Upgrade Script 


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
<td><p>upgradeProductConfiguration_Style</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Product configuration module to support Style.</p></td>
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
<td><p>PCTEMPLATEATTRIBUTE</p></td>
</tr>
<tr class="even">
<td><p>PCTEMPLATE</p></td>
</tr>
</tbody>
</table>


## Remarks

An entry for InventStyleId is added to the \<c\>PCTemplateAttribute\</c\> table. The entry might have been added to the table already and if this is the case, nothing is added.

  


