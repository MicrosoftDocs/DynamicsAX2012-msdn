---
title: ReleaseUpdateDB60_Basic.updateGDL_IT_Intrastat Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateGDL_IT_Intrastat Upgrade Script
ms:assetid: 087e938d-396f-12bd-dc9d-f34fb92952a9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684788(v=AX.60)
ms:contentKeyID: 49706483
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateGDL\_IT\_Intrastat Upgrade Script 


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
<td><p>updateGDL_IT_Intrastat</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ItemType_IT, InvoiceDate, and PaymentMethod_IT fields in the Intrastat table.</p></td>
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
<td><p>InventTable</p></td>
</tr>
<tr class="even">
<td><p>Intrastat</p></td>
</tr>
</tbody>
</table>


## Remarks

Populate \<c\>ItemType\_IT\</c\> field by calling calcItemType\_IT() method in \<c\>Intrastat\</c\> table, \<c\>InvoiceDate\</c\> field from \<c\>TransDate\</c\> of \<c\>Intrastat\</c\> table and \<c\>PaymentMethod\_IT\</c\> field by calling calcPaymentMethod() in \<c\>IntrastatTransferIT\</c\> class.

  


