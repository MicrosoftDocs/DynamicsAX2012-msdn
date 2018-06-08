---
title: ReleaseUpdateDB60_Ledger.allowDupEximDEPBScheduleTable_INProductG Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximDEPBScheduleTable_INProductG Upgrade Script
ms:assetid: 0a522b6c-2981-0261-dee7-d50a63920219
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735614(v=AX.60)
ms:contentKeyID: 49706525
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximDEPBScheduleTable\_INProductG Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupEximDEPBScheduleTable_INProductG</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ProductGroupTableRecIdx index in the EximDEPBScheduleTable_IN table to allow duplicate records.</p></td>
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
<td><p>EXIMDEPBSCHEDULETABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

Previous nonunique index is now unique. Upgrade script required.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

