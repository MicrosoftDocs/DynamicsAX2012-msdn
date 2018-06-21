---
title: ReleaseUpdateDB60_Invent.allowDupInventProdComLineWithoutCodeKeyI
TOCTitle: ReleaseUpdateDB60_Invent.allowDupInventProdComLineWithoutCodeKeyI
ms:assetid: cca012af-3ed2-7669-be3c-6723a669806c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719698(v=AX.60)
ms:contentKeyID: 49711264
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowDupInventProdComLineWithoutCodeKeyI [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>allowDupInventProdComLineWithoutCodeKeyI</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;KeyIdx&lt;/c&gt; in the table &lt;c&gt;InventProdComLineWithoutCode&lt;/c&gt; to allow duplicate records.</p></td>
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

Truncated method name from allowDupInventProdComLineWithoutCodeKeyIdx. The InventProdComPeriodId field is replaced with the new surrogate key field InventProdComTable in the unique index KeyIdx. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId field of the table InventProdComTable.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

