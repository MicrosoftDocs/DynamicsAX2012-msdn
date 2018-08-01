---
title: ReleaseUpdateDB60_smm.updatesmmTMCallListTableWorker Upgrade Script
TOCTitle: ReleaseUpdateDB60_smm.updatesmmTMCallListTableWorker Upgrade Script
ms:assetid: 132f65ca-df4e-a512-242a-19274de64c9b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718482(v=AX.60)
ms:contentKeyID: 49706767
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_smm.updatesmmTMCallListTableWorker Upgrade Script [AX 2012]


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
<td><p>updatesmmTMCallListTableWorker</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_CallResponsibleEmplId field to the CallRespWorker field and the DEL_CallActualEmplId field to the CallActualWorker field in the smmTMCallListTable table.</p></td>
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
<td><p>smmTMCallListTable</p></td>
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
<th><p>From Table: smmTMCallListTable</p></th>
<th><p>To Table: smmTMCallListTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_CallResponsibleEmplId</p></td>
<td><p>CallRespWorker</p></td>
</tr>
<tr class="even">
<td><p>DEL_CallActualEmplId</p></td>
<td><p>CallActualWorker</p></td>
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
<td><p>smmTMCallListTable</p></td>
<td><p>CallRespWorker</p></td>
<td><p>CrmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>smmTMCallListTable</p></td>
<td><p>CallActualWorker</p></td>
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
<td><p>smmTMCallListTable</p></td>
<td><p>DEL_CallResponsibleEmplId</p></td>
</tr>
<tr class="even">
<td><p>smmTMCallListTable</p></td>
<td><p>DEL_CallActualEmplId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

