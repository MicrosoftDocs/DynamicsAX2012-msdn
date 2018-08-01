---
title: ReleaseUpdateDB60_EcoRes.createEcoResTrackingDimGroup
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResTrackingDimGroup
ms:assetid: b22e6399-174a-8a29-d318-35de3a8afb56
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736917(v=AX.60)
ms:contentKeyID: 49710602
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResTrackingDimGroup [AX 2012]


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
<td><p>createEcoResTrackingDimGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new records in the &lt;c&gt;EcoResTrackingDimensionGroup&lt;/c&gt; table. The data is created based on existing data in the &lt;c&gt;InventDimGroup&lt;/c&gt; table. The criterias used for determining how the dimension groups are updated, are specified by the user during the pre-upgrade process.</p></td>
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
<td><p>DEL_EcoResTrackingDimGroupUpgrade</p></td>
</tr>
<tr class="even">
<td><p>EcoResTrackingDimensionGroup</p></td>
</tr>
</tbody>
</table>


## Remarks

The data that the upgrade is dependent on must be provided before upgrade.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

