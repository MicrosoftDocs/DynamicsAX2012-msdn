---
title: ReleaseUpdateDB60_Vend.allowDupVendInvoiceInfoTableSDHederIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.allowDupVendInvoiceInfoTableSDHederIdx Upgrade Script
ms:assetid: 3ae7ff0d-1f07-faa0-1a8d-96734204b7d8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685263(v=AX.60)
ms:contentKeyID: 49707715
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.allowDupVendInvoiceInfoTableSDHederIdx Upgrade Script [AX 2012]


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
<td><p>allowDupVendInvoiceInfoTableSDHederIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SDHeaderIdx index in the VendInvoiceInfoTable table to allow for duplicate records.</p></td>
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

After updating the SourceDocumentHeader field with the value, the SDHeaderIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

