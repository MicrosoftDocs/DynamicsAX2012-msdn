---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximDEPBExportOrderTable_INSch
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximDEPBExportOrderTable_INSch
ms:assetid: cccc223b-85b5-075e-a829-799eb3226c7d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719704(v=AX.60)
ms:contentKeyID: 49711271
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximDEPBExportOrderTable\_INSch 


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
<td><p>allowNoDupEximDEPBExportOrderTable_INSch</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;SchemeTableProductGroupIdx&lt;/c&gt; in the table &lt;c&gt;EximDEPBExportOrderTable_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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

After updating the surrogate key field EximProductGroupTable RecId field of the table, the index SchemeTableProductGroupIdx is reset not to allow duplicate records.

  


