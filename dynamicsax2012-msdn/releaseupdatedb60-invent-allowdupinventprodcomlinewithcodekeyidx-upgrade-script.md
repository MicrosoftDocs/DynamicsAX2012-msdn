---
title: ReleaseUpdateDB60_Invent.allowDupInventProdComLineWithCodeKeyIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.allowDupInventProdComLineWithCodeKeyIdx Upgrade Script
ms:assetid: 08f521f4-193c-befa-a52e-e23a25bdf342
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684799(v=AX.60)
ms:contentKeyID: 49706493
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowDupInventProdComLineWithCodeKeyIdx Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupInventProdComLineWithCodeKeyIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the KeyIdx index in the InventProdComLineWithCode table to allow for duplicate records.</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>InventProdComLineWithCode</p></td>
</tr>
</tbody>
</table>


## Remarks

The InventProdComPeriodId field is replaced with the new surrogate key InventProdComTable field in the unique KeyIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the InventProdComTable table.

  


