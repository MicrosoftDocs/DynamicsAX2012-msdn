---
title: ReleaseUpdateDB60_Trv.updateTrvAppEmplSubWithWorker Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvAppEmplSubWithWorker Upgrade Script
ms:assetid: 731133d8-61ab-0860-a3b3-38a4ce266178
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685817(v=AX.60)
ms:contentKeyID: 49709017
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvAppEmplSubWithWorker Upgrade Script 


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
<td><p>updateTrvAppEmplSubWithWorker</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the AppEmp field to the DelegatedWorker field and Employee field to the DelegatingWorker field in the TrvAppEmplSub table.</p></td>
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
<td><p>TrvAppEmplSub</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade script is needed to convert the employee ID to the new worker for Microsoft Dynamics AX 2012 as part of HCM uptake for Expense Management.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvAppEmplSub</p></th>
<th><p>To Table: TrvAppEmplSub</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_AppEmp</p></td>
<td><p>DelegatedWorker</p></td>
</tr>
<tr class="even">
<td><p>DEL_Employee</p></td>
<td><p>DelegatingWorker</p></td>
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
<td><p>TrvAppEmplSub</p></td>
<td><p>DelegatedWorker</p></td>
<td><p>TrvHcmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>TrvAppEmplSub</p></td>
<td><p>DelegatingWorker</p></td>
<td><p>TrvHcmWorkerRecId</p></td>
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
<td><p>TrvAppEmplSub</p></td>
<td><p>DEL_AppEmp</p></td>
</tr>
<tr class="even">
<td><p>TrvAppEmplSub</p></td>
<td><p>DEL_Employee</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

