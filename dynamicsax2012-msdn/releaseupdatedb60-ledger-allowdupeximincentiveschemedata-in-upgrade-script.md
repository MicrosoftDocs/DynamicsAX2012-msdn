---
title: ReleaseUpdateDB60_Ledger.allowDupEximIncentiveSchemeData_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximIncentiveSchemeData_IN Upgrade Script
ms:assetid: 7c3defde-4fad-188e-5836-1b3eaedae9a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719467(v=AX.60)
ms:contentKeyID: 49709257
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximIncentiveSchemeData\_IN Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>allowDupEximIncentiveSchemeData_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the IncentiveSchemeIdx index in the EximIncentiveSchemeData_IN table to allow for duplicate records.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>EximIncentiveSchemeData_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The IncentiveSchemeGroup field is replaced with the new EximIncentiveSchemeGroup surrogate key field in the IncentiveSchemeIdx index. Initially the EximIncentiveSchemeGroup field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the record ID fields in the EximIncentiveSchemeGroup\_IN table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

