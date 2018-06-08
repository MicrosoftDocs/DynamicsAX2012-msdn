---
title: ReleaseUpdateTransformDB50_Cust.plSysHolidayCalDeltaPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Cust.plSysHolidayCalDeltaPreUpgradeProcess Upgrade Script
ms:assetid: 13da3f84-780c-87d9-34b8-f58267c08611
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718497(v=AX.60)
ms:contentKeyID: 49706781
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Cust.plSysHolidayCalDeltaPreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>plSysHolidayCalDeltaPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the PaymCalendar and PaymCalendarException tables with changes made to the plSysHolidayCalendar table since the preprocessing upgrade was last run.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Accounts payable</p></td>
</tr>
<tr class="even">
<td><p>Accounts receivable</p></td>
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
<td><p>paymCalendar</p></td>
</tr>
<tr class="odd">
<td><p>paymCalendarException</p></td>
</tr>
</tbody>
</table>


## Remarks

The Polish holiday calendar is being replaced by the consolidated functionality of payment calendars. The existing plSysHolidayCalendar table will not be brought forward into Microsoft Dynamics AX 2012. A delta upgrade script is required to populate the new tables with new data from the existing table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

