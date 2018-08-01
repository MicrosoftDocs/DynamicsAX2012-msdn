---
title: ReleaseUpdateDB60_Ledger.allowDupEximExportOrderTable_INAuthoriza Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupEximExportOrderTable_INAuthoriza Upgrade Script
ms:assetid: a0b8b986-277b-d5ba-ed74-ec16ecb4a4f3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736711(v=AX.60)
ms:contentKeyID: 49710142
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupEximExportOrderTable\_INAuthoriza Upgrade Script 


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
<td><p>allowDupEximExportOrderTable_INAuthoriza</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the AuthorizationShippingBillIdx index in the EximExportOrderTable_IN table to allow duplicate records.</p></td>
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
<td><p>EXIMEXPORTORDERTABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The CustomsShippingBillNumber field is replaced with the new CustomsShippingBillNumberTable surrogate key field is replaced in the AuthorizationShippingBillIdx index. Initially the CustomsShippingBillNumberTable field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the EximExportOrderTable\_IN table.

  


