---
title: ReleaseUpdateDB60_Trv.updateTrvCashAdvance Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvCashAdvance Upgrade Script
ms:assetid: d69ba70c-0572-c650-bc85-f0c394ae60ea
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687076(v=AX.60)
ms:contentKeyID: 49711524
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvCashAdvance Upgrade Script 


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
<td><p>updateTrvCashAdvance</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the EmployeeID field to the RequestingWorker field and PaidBy field to the PayingWorker field in the TrvCashAdvance table.</p></td>
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
<td><p>TrvCashAdvance</p></td>
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
<th><p>From Table: TrvCashAdvance</p></th>
<th><p>To Table: TrvCashAdvance</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_EmployeeID</p></td>
<td><p>RequestingWorker</p></td>
</tr>
<tr class="even">
<td><p>DEL_PaidBy</p></td>
<td><p>PayingWorker</p></td>
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
<td><p>TrvCashAdvance</p></td>
<td><p>RequestingWorker</p></td>
<td><p>TrvHcmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>TrvCashAdvance</p></td>
<td><p>PayingWorker</p></td>
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
<td><p>TrvCashAdvance</p></td>
<td><p>DEL_EmployeeID</p></td>
</tr>
<tr class="even">
<td><p>TrvCashAdvance</p></td>
<td><p>DEL_PaidBy</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

