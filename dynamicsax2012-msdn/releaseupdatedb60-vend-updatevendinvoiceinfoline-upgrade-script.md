---
title: ReleaseUpdateDB60_Vend.updateVendInvoiceInfoLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendInvoiceInfoLine Upgrade Script
ms:assetid: f937dc3d-b07c-12d3-a106-50f5c34c41b0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737645(v=AX.60)
ms:contentKeyID: 49712338
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendInvoiceInfoLine Upgrade Script [AX 2012]


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
<td><p>updateVendInvoiceInfoLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the PurchaseLineLineNumber, TaxGroup, TaxItemGroup, and SourceDocumentLine values in the VendInvoiceInfoLine table.</p></td>
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

This method reserves a record in the SourceDocumentLine table and then the RecId value is stored in the SourceDocumentLine field. The TaxGroup, TaxItemGroup, and LineNumber fields are copied from the related PurchLine record.

## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VendInvoiceInfoLine</p></td>
<td><p>SourceDocumentLine</p></td>
<td><p>SourceDocumentLineRecId</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoLine</p></td>
<td><p>PurchaseLineLineNumber</p></td>
<td><p>TradeLineNumber</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoLine</p></td>
<td><p>TaxItemGroup</p></td>
<td><p>TaxItemGroup</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoLine</p></td>
<td><p>TaxGroup</p></td>
<td><p>TaxGroup</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

