---
title: ReleaseUpdateDB60_Vend.updateCustomsImportInvVendAcctSetup_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateCustomsImportInvVendAcctSetup_IN Upgrade Script
ms:assetid: 354d523d-7a38-d55a-3ed6-f7dc8afbb1ec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685147(v=AX.60)
ms:contentKeyID: 49707601
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateCustomsImportInvVendAcctSetup\_IN Upgrade Script [AX 2012]


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
<td><p>updateCustomsImportInvVendAcctSetup_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CustomsImportInvoiceVendAcctSetup_IN table. The record ID of the CustomsImportInvoiceNumberTable_IN table is now stored in place of the CustomsImporterInvoiceNumber_IN field value.</p></td>
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
<tr class="even">
<td><p>CustomsImportInvoiceNumberTable_IN</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomsImportInvoiceVendAcctSetup_IN</p></td>
<td><p>del_ImportInvoiceNumber</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

