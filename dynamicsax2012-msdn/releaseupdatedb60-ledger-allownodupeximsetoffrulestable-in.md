---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximSetOffRulesTable_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximSetOffRulesTable_IN
ms:assetid: 09bac5ed-d117-a48f-94bc-9b6a98ddd5d7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735595(v=AX.60)
ms:contentKeyID: 49706506
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximSetOffRulesTable\_IN 


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
<td><p>allowNoDupEximSetOffRulesTable_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the IncentiveSchemeDataIdx index in the EximSetOffRulesTable_IN table not to allow for duplicate records.</p></td>
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
<td><p>EximSetOffRulesTable_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the EximDEPBSchemesTable surrogate key field with the value of the RecId field of the EximDEPBSchemesTable\_IN table, the IncentiveSchemeDataIdx index is reset not to for allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

