---
title: ReleaseUpdateDB60_Invent.allowNoDupInventProdComLineDetailKeyIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.allowNoDupInventProdComLineDetailKeyIdx Upgrade Script
ms:assetid: c35932df-e420-bd2c-5834-b7a861fb73c4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686830(v=AX.60)
ms:contentKeyID: 49711027
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowNoDupInventProdComLineDetailKeyIdx Upgrade Script 


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
<td><p>allowNoDupInventProdComLineDetailKeyIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the KeyIdx index in the InventProdComLineDetail table not to allow for duplicate records.</p></td>
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
<td><p>InventProdComLineDetail</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key InventProdComTable field with the value of the RecId field of the InventProdComTable table, the KeyIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

