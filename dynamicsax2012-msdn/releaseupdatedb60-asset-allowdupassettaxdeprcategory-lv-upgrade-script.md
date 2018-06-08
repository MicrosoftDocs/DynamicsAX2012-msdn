---
title: ReleaseUpdateDB60_Asset.allowDupAssetTaxDeprCategory_LV Upgrade Script
TOCTitle: ReleaseUpdateDB60_Asset.allowDupAssetTaxDeprCategory_LV Upgrade Script
ms:assetid: a29037cd-e3a5-4f79-bbc8-4cae4013627f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736749(v=AX.60)
ms:contentKeyID: 49710181
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Asset.allowDupAssetTaxDeprCategory\_LV Upgrade Script 


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
<td><p>allowDupAssetTaxDeprCategory_LV</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the indexes in the AssetTaxDeprCategory_LV table to allow duplicate records.</p></td>
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

New fields and indexes have been added to the AssetTaxDeprCategory\_LV table in AX6. Since these fields did not exist in AX5, they will be blank in AX6. Hence, we need to disable the unique indexes in the AssetTaxDeprCategory\_LV table before migrating data from AX5 to AX6.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

