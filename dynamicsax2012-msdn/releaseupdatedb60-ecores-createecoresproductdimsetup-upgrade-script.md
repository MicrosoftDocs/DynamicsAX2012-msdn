---
title: ReleaseUpdateDB60_EcoRes.createEcoResProductDimSetup Upgrade Script
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResProductDimSetup Upgrade Script
ms:assetid: 5ac29b57-a815-1ddb-8b2c-9dfdf34a824a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736310(v=AX.60)
ms:contentKeyID: 49708485
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResProductDimSetup Upgrade Script 


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
<td><p>createEcoResProductDimSetup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new records in the EcoResProductDimensionGroupFldSetup table. The data is created based on existing data in the InventDimSetup table. The criteria that are used for determining how the dimension field setups are updated are specified by the user during the pre-upgrade process.</p></td>
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

The data that the upgrade is dependent on must be provided before the upgrade.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

