---
title: ReleaseUpdateDB60_Ledger.allowDupEximDEPBExportOrderTable_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximDEPBExportOrderTable_IN
ms:assetid: 5c42a0a6-63b8-ce0f-ac02-4f4cca598e48
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736348(v=AX.60)
ms:contentKeyID: 49708521
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximDEPBExportOrderTable\_IN 


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
<td><p>allowDupEximDEPBExportOrderTable_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SchemeTableProductGroupIdx index in the EximDEPBExportOrderTable_IN table to allow for duplicate records.</p></td>
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
<td><p>EximDEPBExportOrderTable_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ProductGroup field is replaced with the new EximProductGroupTableis surrogate key field replaced in the SchemeTableProductGroupIdx unique index. Initially the EximProductGroupTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the EximProductGroupTable\_IN table.

  


