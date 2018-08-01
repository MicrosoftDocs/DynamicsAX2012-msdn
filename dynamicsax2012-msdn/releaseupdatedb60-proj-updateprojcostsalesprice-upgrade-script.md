---
title: ReleaseUpdateDB60_Proj.updateProjCostSalesPrice Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjCostSalesPrice Upgrade Script
ms:assetid: d378134f-5993-c0c2-3cc1-72f5b85a39f3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686977(v=AX.60)
ms:contentKeyID: 49711427
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjCostSalesPrice Upgrade Script 


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
<td><p>updateProjCostSalesPrice</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_EmplId field to the Worker field in the ProjCostSalesPrice table.</p></td>
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
<td><p>Project</p></td>
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
<td><p>ProjCostSalesPrice</p></td>
</tr>
</tbody>
</table>


## Remarks

HCMWorker table and associated tables have replaced the Employee table, that is the EmplTable, and the associated tables in Microsoft Dynamics AX 2012. This transition requires an upgrade.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjCostSalesPrice</p></th>
<th><p>To Table: ProjCostSalesPrice</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_EmplId</p></td>
<td><p>Worker</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ProjCostSalesPrice</p></td>
<td><p>Worker</p></td>
<td><p>ProjWorkerRecId</p></td>
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
<td><p>ProjCostSalesPrice</p></td>
<td><p>DEL_EmplId</p></td>
</tr>
</tbody>
</table>

  


