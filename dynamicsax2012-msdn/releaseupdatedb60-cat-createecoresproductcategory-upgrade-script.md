---
title: ReleaseUpdateDB60_Cat.createEcoResProductCategory Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cat.createEcoResProductCategory Upgrade Script
ms:assetid: b5da0dfa-afb6-5047-7dcb-2fdfa657dacf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737015(v=AX.60)
ms:contentKeyID: 49710697
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cat.createEcoResProductCategory Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cat</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createEcoResProductCategory</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Associates the EcoResProduct table with the EcoResCategory table.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>EcoResProduct</p></td>
</tr>
<tr class="even">
<td><p>EcoResProductCategory</p></td>
</tr>
<tr class="odd">
<td><p>EcoResCategory</p></td>
</tr>
<tr class="even">
<td><p>EcoResCategoryHierarchy</p></td>
</tr>
<tr class="odd">
<td><p>EcoResCategoryHierarchyRole</p></td>
</tr>
<tr class="even">
<td><p>KMConnectionType</p></td>
</tr>
<tr class="odd">
<td><p>SysInfolog</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EcoResCategoryHierarchy</p></th>
<th><p>To Table: EcoResProductCategory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CategoryHierarchy</p></td>
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
<th><p>From Table: EcoResCategory</p></th>
<th><p>To Table: EcoResProductCategory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Category</p></td>
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
<th><p>From Table: EcoResProduct</p></th>
<th><p>To Table: EcoResProductCategory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Product</p></td>
</tr>
</tbody>
</table>

  


