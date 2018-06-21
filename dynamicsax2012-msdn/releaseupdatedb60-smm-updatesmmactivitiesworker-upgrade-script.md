---
title: ReleaseUpdateDB60_smm.updatesmmActivitiesWorker Upgrade Script
TOCTitle: ReleaseUpdateDB60_smm.updatesmmActivitiesWorker Upgrade Script
ms:assetid: 7e90036c-3187-9b5a-16c4-7d0a35dafff9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685854(v=AX.60)
ms:contentKeyID: 49709308
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_smm.updatesmmActivitiesWorker Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_smm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatesmmActivitiesWorker</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_ResponsibleEmployee field to the ResponsibleWorker field and DEL_DoneByEmployee to the DoneByWorker field in the smmActivities table.</p></td>
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
<td><p>CRM</p></td>
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
<td><p>smmActivities</p></td>
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
<th><p>From Table: smmActivities</p></th>
<th><p>To Table: smmActivities</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_ResponsibleEmployee</p></td>
<td><p>ResponsibleWorker</p></td>
</tr>
<tr class="even">
<td><p>DEL_DoneByEmployee</p></td>
<td><p>DoneByWorker</p></td>
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
<td><p>smmActivities</p></td>
<td><p>ResponsibleWorker</p></td>
<td><p>CrmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>smmActivities</p></td>
<td><p>DoneByWorker</p></td>
<td><p>CrmWorkerRecId</p></td>
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
<td><p>smmActivities</p></td>
<td><p>DEL_ResponsibleEmployee</p></td>
</tr>
<tr class="even">
<td><p>smmActivities</p></td>
<td><p>DEL_DoneByEmployee</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

