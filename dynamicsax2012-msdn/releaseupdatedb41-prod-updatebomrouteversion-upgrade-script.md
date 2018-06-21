---
title: ReleaseUpdateDB41_Prod.updateBOMRouteVersion Upgrade Script
TOCTitle: ReleaseUpdateDB41_Prod.updateBOMRouteVersion Upgrade Script
ms:assetid: 8e7d99e7-4d5c-f2d5-571b-19ae22b3d698
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736507(v=AX.60)
ms:contentKeyID: 49709696
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Prod.updateBOMRouteVersion Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBOMRouteVersion</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the inventDimId field to the blank inventDimId field.</p></td>
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
<td><p>Production</p></td>
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
<td><p>BOMVersion</p></td>
</tr>
<tr class="even">
<td><p>RouteVersion</p></td>
</tr>
</tbody>
</table>


## Remarks

The inventDimId field has been added to the BOMVersion and RouteVersion tables. Forms that display the BOMVersion and RouteVersion tables will have an inner join to the InventDim table. This means the inventDimId field must have a reference to an existing InventDim record.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

