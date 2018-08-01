---
title: ReleaseUpdateDB60_Basic.updateHolidayCalendar_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateHolidayCalendar_BR Upgrade Script
ms:assetid: 2fe00630-c24b-281b-e47b-08f7e9135cb7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736041(v=AX.60)
ms:contentKeyID: 49707456
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateHolidayCalendar\_BR Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHolidayCalendar_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Brazilian holiday calendar to the payment calendar.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>DEL_HolidayCalendar_BR</p></td>
</tr>
<tr class="even">
<td><p>PaymCalendar</p></td>
</tr>
<tr class="odd">
<td><p>PaymCalendarCountryRegion</p></td>
</tr>
<tr class="even">
<td><p>PaymCalendarCountryRegionLegalEntity</p></td>
</tr>
<tr class="odd">
<td><p>PaymCalendarException</p></td>
</tr>
<tr class="even">
<td><p>PaymCalendarRule</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HolidayCalendar_BR</p></th>
<th><p>To Table: PaymCalendarException</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HolidayDate</p></td>
<td><p>ExceptionDate</p></td>
</tr>
<tr class="even">
<td><p>Description</p></td>
<td><p>Description</p></td>
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
<td><p>DEL_HolidayCalendar_BR</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

