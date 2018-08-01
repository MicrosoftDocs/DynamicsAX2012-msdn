---
title: ReleaseUpdateDB60_Proj.updateSync Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateSync Upgrade Script
ms:assetid: 9ca16f47-43fe-88af-32c7-97a7a9cea652
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686345(v=AX.60)
ms:contentKeyID: 49710047
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateSync Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateSync</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrade script to store element names instead of IDs.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>SyncSimpleTrans</p></td>
</tr>
<tr class="even">
<td><p>SyncCompoundTrans</p></td>
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
<th><p>From Table: SyncSimpleTrans</p></th>
<th><p>To Table: SyncSimpleTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_SimpleTableId</p></td>
<td><p>SimpleTableName</p></td>
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
<th><p>From Table: SyncCompoundTrans</p></th>
<th><p>To Table: SyncCompoundTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_CompoundTableId</p></td>
<td><p>CompoundTableName</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SyncSimpleTrans</p></td>
<td><p>DEL_SimpleTableId</p></td>
</tr>
<tr class="even">
<td><p>SyncCompoundTrans</p></td>
<td><p>DEL_CompoundTableId</p></td>
</tr>
</tbody>
</table>

  


