---
title: ReleaseUpdateDB60_Proj.updateProjGrantType Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjGrantType Upgrade Script
ms:assetid: 4d9e59c8-20d8-74b1-c5ac-7b1e959df3b9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685443(v=AX.60)
ms:contentKeyID: 49708149
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjGrantType Upgrade Script [AX 2012]


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
<td><p>updateProjGrantType</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_EmployeeContact field to the WorkerContact field and the DEL_GrantManager field to the GrantManagerWorker field in the ProjGrantType table.</p></td>
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
<td><p>ProjGrantType</p></td>
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
<th><p>From Table: ProjGrantType</p></th>
<th><p>To Table: ProjGrantType</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_EmployeeContact</p></td>
<td><p>WorkerContact</p></td>
</tr>
<tr class="even">
<td><p>DEL_GrantManager</p></td>
<td><p>GrantManagerWorker</p></td>
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
<td><p>ProjGrantType</p></td>
<td><p>WorkerContact</p></td>
<td><p>ProjWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>ProjGrantType</p></td>
<td><p>GrantManagerWorker</p></td>
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
<td><p>ProjGrantType</p></td>
<td><p>DEL_EmployeeContact</p></td>
</tr>
<tr class="even">
<td><p>ProjGrantType</p></td>
<td><p>DEL_GrantManager</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

