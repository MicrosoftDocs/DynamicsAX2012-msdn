---
title: ReleaseUpdateDB60_Trv.UpdateTrvEmpPaymethod Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.UpdateTrvEmpPaymethod Upgrade Script
ms:assetid: 527e9e00-6333-94cd-d7c2-b52f55fb22d9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685581(v=AX.60)
ms:contentKeyID: 49708275
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.UpdateTrvEmpPaymethod Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>UpdateTrvEmpPaymethod</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the Employee field to the Worker field in the TrvAppEmplSub table.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>TrvEmpPaymethod</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade script is needed to convert the employee ID to the new worker for Microsoft Dynamics AX 2012 as part of the HCM uptake for Expense Management.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvEmpPaymethod</p></th>
<th><p>To Table: TrvEmpPaymethod</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_Employee</p></td>
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
<td><p>TrvEmpPaymethod</p></td>
<td><p>Worker</p></td>
<td><p>TrvHcmWorkerRecIdT</p></td>
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
<td><p>TrvEmpPaymethod</p></td>
<td><p>DEL_Employee</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

