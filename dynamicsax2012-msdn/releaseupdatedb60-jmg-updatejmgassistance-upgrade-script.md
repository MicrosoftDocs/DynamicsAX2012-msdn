---
title: ReleaseUpdateDB60_Jmg.updateJmgAssistance Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.updateJmgAssistance Upgrade Script
ms:assetid: 47c7ac98-818c-884d-6d79-1dae1e2b67ed
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718986(v=AX.60)
ms:contentKeyID: 49708043
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.updateJmgAssistance Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Jmg</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateJmgAssistance</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the JmgAssistance table to support HcmWorker instead of EmplTable.</p></td>
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
<td><p>Shop Floor Control</p></td>
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
<td><p>JmgAssistance</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
</tr>
<tr class="odd">
<td><p>EmplTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the new WorkerAssistant and WorkerPilot fields with values from the HcmWorker table, based on values from the DEL\_Assistant and DEL\_Pilot tables.

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
<td><p>JmgAssistance</p></td>
<td><p>WorkerAssistant</p></td>
<td><p>JmgWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>JmgAssistance</p></td>
<td><p>WorkerPilot</p></td>
<td><p>JmgWorkerRecId_JobPilot</p></td>
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
<td><p>JmgAssistance</p></td>
<td><p>Assistant</p></td>
</tr>
<tr class="even">
<td><p>JmgAssistance</p></td>
<td><p>Pilot</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

