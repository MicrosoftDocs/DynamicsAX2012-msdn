---
title: ReleaseUpdateDB60_Proj.updateTSAppEmplSub Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateTSAppEmplSub Upgrade Script
ms:assetid: bce97a16-013a-3313-3a09-011c09693f5d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686657(v=AX.60)
ms:contentKeyID: 49710865
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateTSAppEmplSub Upgrade Script 


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
<td><p>updateTSAppEmplSub</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_Employee field to the Worker field and the DEL_AppEmp field to the AppWorker field in the TSAppEmplSub table.</p></td>
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
<td><p>TSAppEmplSub</p></td>
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
<th><p>From Table: TSAppEmplSub</p></th>
<th><p>To Table: TSAppEmplSub</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Employee</p></td>
<td><p>Worker</p></td>
</tr>
<tr class="even">
<td><p>DEL_AppEmp</p></td>
<td><p>AppWorker</p></td>
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
<td><p>TSAppEmplSub</p></td>
<td><p>Worker</p></td>
<td><p>ProjWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>TSAppEmplSub</p></td>
<td><p>AppWorker</p></td>
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
<td><p>TSAppEmplSub</p></td>
<td><p>DEL_Employee</p></td>
</tr>
<tr class="even">
<td><p>TSAppEmplSub</p></td>
<td><p>DEL_AppEmp</p></td>
</tr>
</tbody>
</table>

  


