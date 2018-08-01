---
title: ReleaseUpdateDB60_Ledger.allowDupDimensionAttributeVGHashIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupDimensionAttributeVGHashIdx Upgrade Script
ms:assetid: 197b89af-4cf7-73fa-8839-bc1e0c34ccf8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718631(v=AX.60)
ms:contentKeyID: 49706915
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupDimensionAttributeVGHashIdx Upgrade Script 


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
<td><p>allowDupDimensionAttributeVGHashIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the HashIdx index in the DimensionAttributeValueGroup table to allow for duplicate records.</p></td>
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
<td><p>DimensionAttributeValueGroup</p></td>
</tr>
</tbody>
</table>


## Remarks

Initially this field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the hash fields in the DimensionAttributeValueGroup table.

  


