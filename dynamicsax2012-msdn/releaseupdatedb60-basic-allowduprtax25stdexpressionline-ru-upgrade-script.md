﻿---
title: ReleaseUpdateDB60_Basic.allowDupRTax25StdExpressionLine_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupRTax25StdExpressionLine_RU Upgrade Script
ms:assetid: 0c6252c3-ec85-c964-db58-fb42d25170a6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735681(v=AX.60)
ms:contentKeyID: 49706589
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupRTax25StdExpressionLine\_RU Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupRTax25StdExpressionLine_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SeqLineNumIdx index in the RTax25StdExpressionLine table to allow duplicate records.</p></td>
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
<td><p>RTax25StdExpressionLine</p></td>
</tr>
</tbody>
</table>


## Remarks

The ProfitId field is replaced with the RTax25ProfitTable new surrogate key field in the unique SeqLineNumIdx index. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the record ID field of the RTax25ProfitTable table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

