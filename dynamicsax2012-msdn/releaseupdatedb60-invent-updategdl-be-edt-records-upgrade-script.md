---
title: ReleaseUpdateDB60_Invent.updateGDL_BE_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.updateGDL_BE_EDT_Records Upgrade Script
ms:assetid: 4b1898ab-f2a3-c901-87e0-9a2523bfc49b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685384(v=AX.60)
ms:contentKeyID: 49708074
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.updateGDL\_BE\_EDT\_Records Upgrade Script 


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
<td><p>updateGDL_BE_EDT_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the surrogate key column in the foreign tables with the value from the RecId field of the primary table.</p></td>
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
<td><p>DEL_InventProdComLineWithoutCode</p></td>
</tr>
<tr class="even">
<td><p>InventProdComLineDetail</p></td>
</tr>
<tr class="odd">
<td><p>InventProdComLineWithCode</p></td>
</tr>
<tr class="even">
<td><p>InventProdComTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the InventProdComTable field in the InventProdComLineDetail, InventProdComLineWithCode, and InventProdComLineWithoutCode tables with the value from the RecId field of the InventProdComTable table.

  


