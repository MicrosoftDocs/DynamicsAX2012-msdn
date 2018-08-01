---
title: ReleaseUpdateDB60_Trv.updateTrvExpGuest Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvExpGuest Upgrade Script
ms:assetid: d1af45c5-6ac4-c2c0-230e-3b005e6ebe4c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686939(v=AX.60)
ms:contentKeyID: 49711390
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvExpGuest Upgrade Script 


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
<td><p>updateTrvExpGuest</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates data in the DEL_Type field in the TrvExpGuest table from the Type field in TrvExpTransGuest table. Also, migrates data from the DEL_EmplId field to the CreatingWorker field and the GuestId field to the InternalGuest field in TrvExpGuest table.</p></td>
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
<td><p>TrvExpGuest</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade script is needed to convert the employee ID to the new worker for Microsoft Dynamics AX 2012 as part of HCM uptake for Expense Management. Also, to move the guest type field from the TrvExpTransGuest table to the TrvExpGuest table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvExpTransGuest</p></th>
<th><p>To Table: TrvExpGuest</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Type</p></td>
<td><p>Type</p></td>
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
<th><p>From Table: TrvExpGuest</p></th>
<th><p>To Table: TrvExpGuest</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>GuestId</p></td>
<td><p>InternalGuest</p></td>
</tr>
<tr class="even">
<td><p>DEL_EmplId</p></td>
<td><p>CreatingWorker</p></td>
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
<td><p>TrvExpGuest</p></td>
<td><p>InternalGuest</p></td>
<td><p>TrvHcmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>TrvExpGuest</p></td>
<td><p>CreatingWorker</p></td>
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
<td><p>TrvExpGuest</p></td>
<td><p>DEL_EmplId</p></td>
</tr>
</tbody>
</table>

  


