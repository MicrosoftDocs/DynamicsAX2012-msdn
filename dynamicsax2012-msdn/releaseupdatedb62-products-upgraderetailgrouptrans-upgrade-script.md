---
title: ReleaseUpdateDB62_Products.upgradeRetailGroupTrans Upgrade Script
TOCTitle: ReleaseUpdateDB62_Products.upgradeRetailGroupTrans Upgrade Script
ms:assetid: 15635d0b-28ec-b804-218d-72f3b568ee57
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn975038(v=AX.60)
ms:contentKeyID: 65236152
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Products.upgradeRetailGroupTrans Upgrade Script 


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
<td><p>upgradeRetailGroupTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades retail dimension groups.</p></td>
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
<td><p>RetailSizeGroupTrans</p></td>
</tr>
<tr class="even">
<td><p>RetailColorGroupTrans</p></td>
</tr>
<tr class="odd">
<td><p>RetailStyleGroupTrans</p></td>
</tr>
<tr class="even">
<td><p>RetailSizeGroupTransTranslation</p></td>
</tr>
<tr class="odd">
<td><p>RetailColorGroupTransTranslation</p></td>
</tr>
<tr class="even">
<td><p>RetailStyleGroupTransTranslation</p></td>
</tr>
</tbody>
</table>


## Remarks

The names of product master dimension values are moved to RetailXxxxGroupTransTranslation to enable translation.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: RetailSizeGroupTrans</p></th>
<th><p>To Table: RetailSizeGroupTransTranslation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Name</p></td>
<td><p>Name</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: RetailColorGroupTrans</p></th>
<th><p>To Table: RetailColorGroupTransTranslation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Name</p></td>
<td><p>Name</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: RetailStyleGroupTrans</p></th>
<th><p>To Table: RetailStyleGroupTransTranslation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Name</p></td>
<td><p>Name</p></td>
</tr>
</tbody>
</table>

  


