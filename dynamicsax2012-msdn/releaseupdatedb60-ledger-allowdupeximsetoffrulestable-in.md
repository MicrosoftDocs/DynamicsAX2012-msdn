---
title: ReleaseUpdateDB60_Ledger.allowDupEximSetOffRulesTable_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximSetOffRulesTable_IN
ms:assetid: e749f035-6f40-d9f1-2184-0b7fe0c77811
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719823(v=AX.60)
ms:contentKeyID: 49711896
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximSetOffRulesTable\_IN 


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
<td><p>allowDupEximSetOffRulesTable_IN</p></td>
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

The SchemeId field is replaced with the new EximDEPBSchemesTable surrogate key field is replaced in IncentiveSchemeDataIdx unique index. Initially the EximDEPBSchemesTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields in the EximDEPBSchemesTable\_IN table.

  


