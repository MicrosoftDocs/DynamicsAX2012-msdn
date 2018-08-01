﻿---
title: ReleaseUpdateDB60_PBA.updatePBATreeRouteOpr Upgrade Script
TOCTitle: ReleaseUpdateDB60_PBA.updatePBATreeRouteOpr Upgrade Script
ms:assetid: 89790ea9-81cd-0f76-b72a-e9d5734c22a8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736377(v=AX.60)
ms:contentKeyID: 49709569
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PBA.updatePBATreeRouteOpr Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_PBA</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePBATreeRouteOpr</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates WrkCtrpbaTreeRouteOprActivity, WrkCtrActivity, WrkCtrActivityRequirementSet, and WrkCtrActivityRequirement tables,</p></td>
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
<td><p>Product Builder</p></td>
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
<td><p>DEL_PBATreeRouteWrkCtrFixing</p></td>
</tr>
<tr class="even">
<td><p>PBATreeRouteOpr</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivity</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrActivityCapabilityRequirement</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivityRequirement</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrActivityRequirementSet</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrActivityResourceGroupRequirement</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrActivityResourceRequirement</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrCapability</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrCapabilityResource</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrPBATreeRouteOprActivity</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrResourceGroup</p></td>
</tr>
<tr class="odd">
<td><p>WrkCtrResourceGroupResource</p></td>
</tr>
<tr class="even">
<td><p>WrkCtrTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The resource model introduced in Microsoft Dynamics AX 2012 has a different database schema and requires that the resource information from the route operation nodes be migrated to the respective tables.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

