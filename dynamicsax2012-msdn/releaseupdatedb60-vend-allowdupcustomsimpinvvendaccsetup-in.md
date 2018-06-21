---
title: ReleaseUpdateDB60_Vend.allowDupCustomsImpInvVendAccSetup_IN
TOCTitle: ReleaseUpdateDB60_Vend.allowDupCustomsImpInvVendAccSetup_IN
ms:assetid: ef09a92f-d66d-52ac-ecb6-5d0299abd563
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720032(v=AX.60)
ms:contentKeyID: 49712084
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.allowDupCustomsImpInvVendAccSetup\_IN [AX 2012]


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

The ImportInvoiceNumber field is replaced with the new Reference surrogate key field in the unique AccountNumIdx index. Initially the CustomsImportInvoiceNumberTable field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the RecId fields of the CustomsImportInvoiceNumberTable\_IN table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

