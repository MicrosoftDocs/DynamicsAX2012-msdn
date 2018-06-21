---
title: ReleaseUpdateDB60_Invent.allowDupInventProdComLineDetailKeyIdx
TOCTitle: ReleaseUpdateDB60_Invent.allowDupInventProdComLineDetailKeyIdx
ms:assetid: 5d848d68-af40-d932-f56a-433aac8c13ae
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719008(v=AX.60)
ms:contentKeyID: 49708547
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowDupInventProdComLineDetailKeyIdx [AX 2012]


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
<td><p>allowDupInventProdComLineDetailKeyIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the key index in the &lt;c&gt;InventProdComLineDetail&lt;/c&gt; table to allow duplicate records.</p></td>
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

The \<c\>InventProdComPeriodId\</c\> value is replaced by the key index of a record in the \<c\>InventProdComTable\</c\> table.Initially this field contains no value. The index is set to allow duplicates before the field is updated with the record ID of the \<c\>InventProdComTable\</c\> table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

