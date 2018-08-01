---
title: ReleaseUpdateTransformDB40_Cust.plSysHolidayCalendarPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Cust.plSysHolidayCalendarPreUpgradeProcess Upgrade Script
ms:assetid: 2894fac8-f302-1265-3eff-de17f906ea7c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735869(v=AX.60)
ms:contentKeyID: 49707287
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Cust.plSysHolidayCalendarPreUpgradeProcess Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>plSysHolidayCalendarPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the PaymCalendar and PaymCalendarException tables with dates from the plSysHolidayCalendar table.</p></td>
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
<td><p>Accounts receivable</p></td>
</tr>
<tr class="even">
<td><p>Accounts payable</p></td>
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
<td><p>plSysHolidayCalendar</p></td>
</tr>
<tr class="even">
<td><p>PaymCalendar</p></td>
</tr>
<tr class="odd">
<td><p>PaymCalendarException</p></td>
</tr>
</tbody>
</table>


## Remarks

The Polish holiday calendar is being replaced by the consolidated functionality of payment calendars. The existing plSysHolidayCalendar table will not be brought forward into Microsoft Dynamics AX 2012. Upgrade scripts are required to populate the new tables with data from the existing table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

