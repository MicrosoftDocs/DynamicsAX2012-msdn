---
title: ReleaseUpdateDB60_Ledger.allowDupEximSionTable_INProductGroupVali Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximSionTable_INProductGroupVali Upgrade Script
ms:assetid: bccfded8-b6bc-43d4-fd2b-8cc3a5911c6b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686653(v=AX.60)
ms:contentKeyID: 49710861
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximSionTable\_INProductGroupVali Upgrade Script 


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
<td><p>allowDupEximSionTable_INProductGroupVali</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ProductGroupValidFromValidToIdx index in the EximSionTable_IN table to allow duplicate records.</p></td>
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
<td><p>EXIMSIONTABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ProductGroup field is replaced with the new EximProductGroupTable surrogate key field along with the date effectivity fields in the new unique ProductGroupValidFromToIdx index. Initially the EximProductGroupTable, ValidFrom, and ValidTo fields contain no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the EximProductGroupTable\_IN table.

  


