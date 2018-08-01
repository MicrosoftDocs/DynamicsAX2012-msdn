---
title: ReleaseUpdateDB60_Ledger.updateGDL_BE_EDT_Records
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_BE_EDT_Records
ms:assetid: 0514bf38-5ca9-f438-e546-194bb32ed6e7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684714(v=AX.60)
ms:contentKeyID: 49706410
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_BE\_EDT\_Records 


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
<td><p>updateGDL_BE_EDT_Records</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>TaxEdivatDetail</p></td>
</tr>
<tr class="even">
<td><p>TaxEdivatErrors</p></td>
</tr>
<tr class="odd">
<td><p>TaxEdivatGeneral</p></td>
</tr>
<tr class="even">
<td><p>TaxEdivatReturnedErrors</p></td>
</tr>
<tr class="odd">
<td><p>TaxIntervatDetail</p></td>
</tr>
<tr class="even">
<td><p>TaxIntervatGeneral</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the \<c\>TaxIntervatGeneral\</c\> field in the tables \<c\>TaxIntervatDetail\</c\> with the value from the \<c\>RecId\</c\> field of the \<c\>TaxIntervatGeneral\</c\> table. Updates the \<c\>TaxEdivatErrors\</c\> field in the tables \<c\>TaxEdivatReturnedErrors\</c\> with the value from the \<c\>RecId\</c\> field of the \<c\>TaxEdivatErrors\</c\> table. Updates the \<c\>TaxEdivatGeneral\</c\> field in the tables \<c\>TaxEdivatReturnedErrors\</c\> and \<c\>TaxEdivatDetail\</c\> with the value from the \<c\>RecId\</c\> field of the \<c\>TaxEdivatGeneral\</c\> table.

  


