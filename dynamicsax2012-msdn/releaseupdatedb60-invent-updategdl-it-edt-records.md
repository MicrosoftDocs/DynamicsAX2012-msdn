---
title: ReleaseUpdateDB60_Invent.updateGDL_IT_EDT_Records
TOCTitle: ReleaseUpdateDB60_Invent.updateGDL_IT_EDT_Records
ms:assetid: 7462d63d-dee5-48b1-5c0b-cbb79617f851
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719275(v=AX.60)
ms:contentKeyID: 49709067
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.updateGDL\_IT\_EDT\_Records 


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
<td><p>updateGDL_IT_EDT_Records</p></td>
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
<td><p>InventFiscalLIFOGroup</p></td>
</tr>
<tr class="even">
<td><p>InventFiscalLIFOJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>InventFiscalLIFOJournalTransAdj</p></td>
</tr>
<tr class="even">
<td><p>InventTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the \<c\>InventFiscalLIFOGroup\</c\> field in the tables \<c\>InventFiscalLIFOJournalTrans\</c\>, \<c\>InventFiscalLIFOJournalTransAdj\</c\> and \<c\>InventTable\</c\> with the value from the \<c\> RecId\</c\> field of the \<c\>InventFiscalLIFOGroup\</c\> table.

  


