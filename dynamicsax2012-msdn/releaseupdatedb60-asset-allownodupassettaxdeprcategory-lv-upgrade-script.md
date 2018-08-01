---
title: ReleaseUpdateDB60_Asset.allowNoDupAssetTaxDeprCategory_LV Upgrade Script
TOCTitle: ReleaseUpdateDB60_Asset.allowNoDupAssetTaxDeprCategory_LV Upgrade Script
ms:assetid: 8a404c74-028d-1541-c6cb-6845d15628ec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736397(v=AX.60)
ms:contentKeyID: 49709587
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Asset.allowNoDupAssetTaxDeprCategory\_LV Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Asset</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupAssetTaxDeprCategory_LV</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the indexes in the AssetTaxDeprCategory_LV table to not allow duplicate records.</p></td>
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
<td><p>Fixed Asset</p></td>
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
<td><p>AssetTaxDeprCategory_LV</p></td>
</tr>
</tbody>
</table>


## Remarks

After the data has been migrated from AX5 to AX6 and missing data has been fixed, this method turns on the indexes in the AssetTaxDeprCategory\_LV table in order to enforce the uniqueness constraint.

  


