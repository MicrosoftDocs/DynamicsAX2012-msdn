---
title: ReleaseUpdateDB60_EMS.updateEMSDailyFlow Upgrade Script
TOCTitle: ReleaseUpdateDB60_EMS.updateEMSDailyFlow Upgrade Script
ms:assetid: 3b3d4cc7-4017-6a0e-dd53-bf9528a1ada5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685275(v=AX.60)
ms:contentKeyID: 49707726
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EMS.updateEMSDailyFlow Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_EMS</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEMSDailyFlow</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the EMSDailyFlow table.</p></td>
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
<td><p>Environment</p></td>
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
<td><p>EMSFlow</p></td>
</tr>
<tr class="even">
<td><p>EMSDailyFlow</p></td>
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
<th><p>From Table: EMSFlow</p></th>
<th><p>To Table: EMSDailyFlow</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FlowId</p></td>
<td><p>RefFlowId</p></td>
</tr>
<tr class="even">
<td><p>StartDate</p></td>
<td><p>FlowDate</p></td>
</tr>
<tr class="odd">
<td><p>SubstanceBaseQty</p></td>
<td><p>SubstanceBaseQtyByDay</p></td>
</tr>
<tr class="even">
<td><p>AmountPercentage</p></td>
<td><p>AmountPercentageByDay</p></td>
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
<td><p>EMSDailyFlow</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

