---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximSionTable_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximSionTable_IN Upgrade Script
ms:assetid: 19a4e89c-8c87-8837-399d-3d72fc04bc32
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718635(v=AX.60)
ms:contentKeyID: 49706936
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximSionTable\_IN Upgrade Script 


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
<td><p>allowNoDupEximSionTable_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ProductGroupValidFromValidToIdx index in the EximSionTable_IN table not to allow for duplicate records.</p></td>
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
<td><p>EximSionTable_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the EximProductGroupTable, ValidFrom, and ValidTo surrogate key fields with the value of the record ID field of the EximSionTable\_IN table, the ProductGroupValidFromToIdx index is reset not to allow for duplicate records.

  


