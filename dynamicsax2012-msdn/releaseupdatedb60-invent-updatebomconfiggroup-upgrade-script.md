﻿---
title: ReleaseUpdateDB60_Invent.updateBOMConfigGroup Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.updateBOMConfigGroup Upgrade Script
ms:assetid: a30f380b-9b67-fcbf-2ffa-c65047fc35c3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736756(v=AX.60)
ms:contentKeyID: 49710188
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.updateBOMConfigGroup Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBOMConfigGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the configGroupId fields in the BOM table and the ConfigChoice table as the ConfigChoice.BOMRefRecId field is removed.</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>BOM</p></td>
</tr>
<tr class="even">
<td><p>CONFIGCHOICE</p></td>
</tr>
<tr class="odd">
<td><p>CONFIGGROUP</p></td>
</tr>
<tr class="even">
<td><p>BOMPARAMETERS</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

