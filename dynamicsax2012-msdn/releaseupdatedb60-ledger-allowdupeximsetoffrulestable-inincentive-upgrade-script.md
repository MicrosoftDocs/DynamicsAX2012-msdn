---
title: ReleaseUpdateDB60_Ledger.allowDupEximSetOffRulesTable_INIncentive Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximSetOffRulesTable_INIncentive Upgrade Script
ms:assetid: 76ae948f-a371-2fed-8444-242489f624f7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719340(v=AX.60)
ms:contentKeyID: 49709131
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximSetOffRulesTable\_INIncentive Upgrade Script 


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
<td><p>allowDupEximSetOffRulesTable_INIncentive</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the IncentiveSchemeDataIdx index in the EximSetOffRulesTable_IN table to allow duplicate records.</p></td>
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

The SchemeId field is replaced with the new EximDEPBSchemesTable surrogate key field is replaced in the IncentiveSchemeDataIdx index. Initially the EximDEPBSchemesTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the EximDEPBSchemesTable\_IN table.

  


