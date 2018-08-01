---
title: ReleaseUpdateDB60_Vend.allowNoDupVendInvoiceInfoTableSDHederIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.allowNoDupVendInvoiceInfoTableSDHederIdx Upgrade Script
ms:assetid: 3c8ec0c9-2694-b30d-e369-f8e1a54a837a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685303(v=AX.60)
ms:contentKeyID: 49707739
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.allowNoDupVendInvoiceInfoTableSDHederIdx Upgrade Script [AX 2012]


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
<td><p>allowNoDupVendInvoiceInfoTableSDHederIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SDHeaderIdx index in the VendInvoiceInfoTable table not to allow for duplicate records.</p></td>
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
<td><p>VendInvoiceInfoTable</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the SourceDocumentHeader field with the value, the SDHeaderIdx index is reset to not allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

