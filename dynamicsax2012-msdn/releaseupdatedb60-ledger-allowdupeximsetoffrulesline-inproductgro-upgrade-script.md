---
title: ReleaseUpdateDB60_Ledger.allowDupEximSetOffRulesLine_INProductGro Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximSetOffRulesLine_INProductGro Upgrade Script
ms:assetid: 793b7715-2001-78ae-9f17-9d9835f59f64
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719392(v=AX.60)
ms:contentKeyID: 49709183
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximSetOffRulesLine\_INProductGro Upgrade Script 


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
<td><p>allowDupEximSetOffRulesLine_INProductGro</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ProductGroupSetOffRulesIdx index in the EximSetOffRulesLine_IN table to allow duplicate records.</p></td>
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
<td><p>EXIMSETOFFRULESLINE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ProductGroup field is replaced with the new EximProductGroupTable surrogate key field is replaced in the ProductGroupSetOffRulesIdx index. Initially the EximProductGroupTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the EximProductGroupTable\_IN table.

  


