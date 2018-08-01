---
title: ReleaseUpdateDB60_Vend.allowDupCustomsImpInvVendAccSetup_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.allowDupCustomsImpInvVendAccSetup_IN Upgrade Script
ms:assetid: 23dd1b64-5135-b895-ada5-24996a4eefbe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684980(v=AX.60)
ms:contentKeyID: 49707181
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.allowDupCustomsImpInvVendAccSetup\_IN Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupCustomsImpInvVendAccSetup_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the AccountNumIdx index in the CustomsImportInvoiceVendAcctSetup_IN table to allow for duplicate records.</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>CustomsImportInvoiceVendAcctSetup_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The ImportInvoiceNumber field is replaced with the new surrogate key field reference in the AccountNumIdx unique index. Initially the CustomsImportInvoiceNumberTable field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the record ID field of the CustomsImportInvoiceNumberTable\_IN table.

  


