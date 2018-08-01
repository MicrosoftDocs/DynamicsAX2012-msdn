---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximSionTable_INProductGroupVa Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximSionTable_INProductGroupVa Upgrade Script
ms:assetid: d2f512a8-4c1c-abab-4dc2-d4cb9a875108
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686965(v=AX.60)
ms:contentKeyID: 49711415
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximSionTable\_INProductGroupVa Upgrade Script 


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
<td><p>allowNoDupEximSionTable_INProductGroupVa</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ProductGroupValidFromValidToIdx index in the EximSionTable_IN table to not allow duplicate records.</p></td>
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

After updating the EximProductGroupTable surrogate key field, The ValidFrom and ValidTo fields with the value of the RecId field of the table, the ProductGroupValidFromToIdx index is reset to not allow duplicate records.

  


