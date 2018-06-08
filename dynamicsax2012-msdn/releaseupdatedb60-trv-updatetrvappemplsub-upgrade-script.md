---
title: ReleaseUpdateDB60_Trv.updateTrvAppEmplSub Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvAppEmplSub Upgrade Script
ms:assetid: 5d7423cf-c6b8-1835-b1c0-397044aeff23
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736354(v=AX.60)
ms:contentKeyID: 49708528
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvAppEmplSub Upgrade Script 


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
<td><p>updateTrvAppEmplSub</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the data in the TrvAppEmplSub table, which is the delegate information.</p></td>
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
<tr class="even">
<td><p>DirPersonUser</p></td>
</tr>
<tr class="odd">
<td><p>UserInfo</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Before this upgrade, the delegation was using the TrvReportDate field in the TrvExpTable table. The TrvReportDate field is removed and, for delegation purposes, we are using the system-supplied Created Date Time. This upgrade converts the DateFrom and DateTo fields to UTC times, into FromDateUTC and ToDateUTC fields, respectively. Since the FromDateUTC field represents the beginning of the day on the given date, the time portion of this UTC field is always 0, which represents 00:00:00 hours. Similarly, since the ToDateUTC field represents the end of the day on the given date, the time portion of this UTC field is 23:59:59 hours.

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
<td><p>DateFrom</p></td>
<td><p>FromDateUTC</p></td>
</tr>
<tr class="even">
<td><p>DateTo</p></td>
<td><p>ToDateUTC</p></td>
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
<td><p>DateFrom</p></td>
</tr>
<tr class="even">
<td><p>TrvAppEmplSub</p></td>
<td><p>DateTo</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

