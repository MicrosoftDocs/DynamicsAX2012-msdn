﻿---
title: ReleaseUpdateDB60_Invent.allowNoDupInventProdComLineWithoutCodeKe Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.allowNoDupInventProdComLineWithoutCodeKe Upgrade Script
ms:assetid: e1af9739-67f3-66b8-8214-b417f5ec263f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737330(v=AX.60)
ms:contentKeyID: 49711772
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowNoDupInventProdComLineWithoutCodeKe Upgrade Script [AX 2012]


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
<td><p>allowNoDupInventProdComLineWithoutCodeKe</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the KeyIdx index in the InventProdComLineWithoutCode table not to allow for duplicate records.</p></td>
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
</tbody>
</table>


## Remarks

The name of this method is truncated from allowNoDupInventProdComLineWithoutCodeKeyIdx. After updating the surrogate key InventProdComTable field with the value of the RecId field of the InventProdComTable table, the KeyIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

