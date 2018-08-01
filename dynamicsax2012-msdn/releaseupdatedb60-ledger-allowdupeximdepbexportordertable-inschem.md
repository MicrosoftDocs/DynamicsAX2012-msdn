---
title: ReleaseUpdateDB60_Ledger.allowDupEximDEPBExportOrderTable_INSchem
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximDEPBExportOrderTable_INSchem
ms:assetid: 17276632-8eb5-0506-ebdb-3f82b2ae2e50
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718572(v=AX.60)
ms:contentKeyID: 49706856
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximDEPBExportOrderTable\_INSchem 


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
<td><p>allowDupEximDEPBExportOrderTable_INSchem</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;SchemeTableProductGroupIdx&lt;/c&gt; in the table &lt;c&gt;EximDEPBExportOrderTable_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>EXIMDEPBEXPORTORDERTABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ProductGroup field is replaced with the new surrogate key field EximProductGroupTableis replaced in SchemeTableProductGroupIdx. Initially the EximProductGroupTablefield contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the table EximProductGroupTable\_IN.

  


