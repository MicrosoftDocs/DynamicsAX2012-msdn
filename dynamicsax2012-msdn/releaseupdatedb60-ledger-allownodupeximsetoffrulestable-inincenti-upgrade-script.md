---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximSetOffRulesTable_INIncenti Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximSetOffRulesTable_INIncenti Upgrade Script
ms:assetid: 2fa899a0-4889-7bc5-b910-fdec3971930a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736042(v=AX.60)
ms:contentKeyID: 49707457
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximSetOffRulesTable\_INIncenti Upgrade Script 


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
<td><p>allowNoDupEximSetOffRulesTable_INIncenti</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the IncentiveSchemeDataIdx index in the EximSetOffRulesTable_IN table not to allow duplicate records.</p></td>
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
<td><p>EXIMSETOFFRULESTABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the EximDEPBSchemesTable surrogate key field the RecId field of the EximDEPBSchemesTable\_IN table, the IncentiveSchemeDataIdx index is reset to not allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

