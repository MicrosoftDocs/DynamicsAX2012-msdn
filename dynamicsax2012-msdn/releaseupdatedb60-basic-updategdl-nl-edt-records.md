﻿---
title: ReleaseUpdateDB60_Basic.updateGDL_NL_EDT_Records
TOCTitle: ReleaseUpdateDB60_Basic.updateGDL_NL_EDT_Records
ms:assetid: f61185ec-d30d-387a-c734-ef76c5d758b0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737554(v=AX.60)
ms:contentKeyID: 49712248
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateGDL\_NL\_EDT\_Records 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateGDL_NL_EDT_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the surrogate key column in the foreign tables with the value from the &lt;c&gt;RecId&lt;/c&gt; field of the primary table.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>PaymInstruction</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the \<c\>PaymInstruction1\</c\>, \<c\>PaymInstruction2\</c\>, \<c\>PaymInstruction3\</c\> and \<c\>PaymInstruction4\</c\> fields in the table \<c\>CompanyInfo\</c\> with the value from the \<c\>RecId\</c\> field of the \<c\>PaymInstruction\</c\> table.

  


