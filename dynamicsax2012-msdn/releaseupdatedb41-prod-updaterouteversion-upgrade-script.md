---
title: ReleaseUpdateDB41_Prod.updateRouteVersion Upgrade Script
TOCTitle: ReleaseUpdateDB41_Prod.updateRouteVersion Upgrade Script
ms:assetid: 829fe472-620f-16a7-7ca1-5cfbdbab4b1c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685954(v=AX.60)
ms:contentKeyID: 49709407
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Prod.updateRouteVersion Upgrade Script 


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
<td><p>updateRouteVersion</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the inventDimId field to empty.</p></td>
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
<td><p>RouteVersion</p></td>
</tr>
</tbody>
</table>


## Remarks

A new field that is named inventDimId has been added to the RouteVersion table. Forms that show the RouteVersion table will have an innerjoin to the inventDim table. The inventDimId field must have a reference to an existing inventDim record.

  


