---
title: ReleaseUpdateDB60_EcoRes.createEcoResStorageDimSetup Upgrade Script
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResStorageDimSetup Upgrade Script
ms:assetid: 4c7b47f4-5a1c-6c60-e32f-ca7b1644c0cd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685410(v=AX.60)
ms:contentKeyID: 49708115
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResStorageDimSetup Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>createEcoResStorageDimSetup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new records in the EcoResStorageDimensionGroupFldSetup table.</p></td>
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
<td><p>EcoResStorageDimensionGroup</p></td>
</tr>
<tr class="even">
<td><p>EcoResStorageDimensionGroupFldSetup</p></td>
</tr>
</tbody>
</table>


## Remarks

The data is created by using existing data in the InventDimSetup table. The criteria that is used for determining how the dimension field setups are updated are specified by the user during the pre-upgrade process. The data that the upgrade depends on must be provided before upgrade.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

