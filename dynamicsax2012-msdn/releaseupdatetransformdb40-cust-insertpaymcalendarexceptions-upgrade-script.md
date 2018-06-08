---
title: ReleaseUpdateTransformDB40_Cust.insertPaymCalendarExceptions Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Cust.insertPaymCalendarExceptions Upgrade Script
ms:assetid: 0b7ce096-6e3d-2cd8-72ac-c504b1631833
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735650(v=AX.60)
ms:contentKeyID: 49706561
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Cust.insertPaymCalendarExceptions Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>insertPaymCalendarExceptions</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script populates the calendar exception table from the polish payment calendar table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>PaymCalendarException</p></td>
</tr>
</tbody>
</table>


## Remarks

Populates the \<c\>PaymCalendarException\</c\> table from the PlSysHolidayCalendar table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PlSysHolidayCalendar</p></th>
<th><p>To Table: PaymCalendarException</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HolidayDescription</p></td>
<td><p>Description</p></td>
</tr>
<tr class="even">
<td><p>HolidayDate</p></td>
<td><p>ExceptionDate</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

