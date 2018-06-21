---
title: ReleaseUpdateDB60_Vend.allowNoDupVendInvoiceInfoLineSourceDocum Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.allowNoDupVendInvoiceInfoLineSourceDocum Upgrade Script
ms:assetid: 43b19cda-335c-6fa4-182e-5264fba0cb02
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718877(v=AX.60)
ms:contentKeyID: 49707921
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.allowNoDupVendInvoiceInfoLineSourceDocum Upgrade Script [AX 2012]


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
<td><p>allowNoDupVendInvoiceInfoLineSourceDocum</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SourceDocumentLine index in the VendInvoiceInfoLine table not to allow for duplicate records.</p></td>
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
<td><p>VendInvoiceInfoLine</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the SourceDocumentLine field with the value, the SourceDocumentLine index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

