---
title: ReleaseUpdateDB60_Proj.updateProjTransPosting Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjTransPosting Upgrade Script
ms:assetid: c3148940-4c85-1e55-c0dd-ec370bc6c600
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686837(v=AX.60)
ms:contentKeyID: 49711034
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjTransPosting Upgrade Script 


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
<td><p>updateProjTransPosting</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the EmplItemId field to the Worker field in the ProjTransPosting table when the value of the ProjTransType field is the Revenue value or the Cost or Hour value.</p></td>
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
<td><p>ProjTransPosting</p></td>
</tr>
</tbody>
</table>


## Remarks

The HCMWorker table and associated tables have replaced the Employee table, that is the EmplTable table, and associated tables in Microsoft Dynamics AX 2012. This transition requires an upgrade.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjTransPosting</p></th>
<th><p>To Table: ProjTransPosting</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EmplItemId</p></td>
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
<td><p>ProjTransPosting</p></td>
<td><p>Worker</p></td>
<td><p>ProjWorkerRecId</p></td>
</tr>
</tbody>
</table>

  


