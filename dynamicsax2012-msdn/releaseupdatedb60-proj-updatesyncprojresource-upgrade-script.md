---
title: ReleaseUpdateDB60_Proj.updateSyncProjResource Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateSyncProjResource Upgrade Script
ms:assetid: d6523225-7fc0-9193-28be-91057cd987fd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687065(v=AX.60)
ms:contentKeyID: 49711513
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateSyncProjResource Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateSyncProjResource</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Microsoft Dynamics AX 2009 used the validation table to store the team information from the project server. This data is moved to the ProjResource table.</p></td>
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
<td><p>Project</p></td>
</tr>
<tr class="even">
<td><p>Project</p></td>
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
<td><p>ProjResource</p></td>
</tr>
<tr class="even">
<td><p>ProjValEmplProjSetup</p></td>
</tr>
</tbody>
</table>


## Remarks

It requires the project that was integrated with the project server in Microsoft Dynamics AX 2009. The employee was integrated with the project server in Microsoft Dynamics AX 2009. During the upgrade, it depends on the resource that is created for the integrated employee, which is also marked as "integrated enabled".

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: syncProjValEmplProjSetup</p></th>
<th><p>To Table: projResource</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<th><p>From Table: syncProjValEmplProjSetup</p></th>
<th><p>To Table: syncProjResource</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

