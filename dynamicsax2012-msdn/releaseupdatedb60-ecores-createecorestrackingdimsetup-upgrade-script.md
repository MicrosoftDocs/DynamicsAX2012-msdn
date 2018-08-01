---
title: ReleaseUpdateDB60_EcoRes.createEcoResTrackingDimSetup Upgrade Script
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResTrackingDimSetup Upgrade Script
ms:assetid: 0b755707-0fb2-7556-53e2-6108605ec995
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735648(v=AX.60)
ms:contentKeyID: 49706559
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResTrackingDimSetup Upgrade Script [AX 2012]


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
<td><p>createEcoResTrackingDimSetup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new records in the EcoResTrackingDimensionGroupFldSetup table. The data is created based on existing data in the InventDimSetup table. The criteria that are used for determining how the dimension field setups are updated are specified by the user during the pre-upgrade process.</p></td>
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
<td><p>EcoResTrackingDimensionGroup</p></td>
</tr>
<tr class="even">
<td><p>EcoResTrackingDimensionGroupFldSetup</p></td>
</tr>
<tr class="odd">
<td><p>DEL_InventDimSetup</p></td>
</tr>
<tr class="even">
<td><p>DEL_EcoResDimGroupUpgrade</p></td>
</tr>
</tbody>
</table>


## Remarks

The data that the upgrade is dependent on must be provided before the upgrade.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

