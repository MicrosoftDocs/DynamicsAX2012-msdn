---
title: ReleaseUpdateDB60_Cust.updateCustInvoicePackingSlipQtyMatch Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustInvoicePackingSlipQtyMatch Upgrade Script
ms:assetid: 14792e3f-eabc-7e4b-59eb-0230f127292b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718512(v=AX.60)
ms:contentKeyID: 49706795
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustInvoicePackingSlipQtyMatch Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCustInvoicePackingSlipQtyMatch</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the CustInvoicePackingSlipQuantityMatch table for matching sales packing slips and sales invoices for open sales orders.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>CustInvoiceJour</p></td>
</tr>
<tr class="even">
<td><p>CustInvoicePackingSlipQuantityMatch</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTrans</p></td>
</tr>
<tr class="even">
<td><p>CustPackingSlipJour</p></td>
</tr>
<tr class="odd">
<td><p>CustPackingSlipTrans</p></td>
</tr>
<tr class="even">
<td><p>InventTrans</p></td>
</tr>
<tr class="odd">
<td><p>InventTransOrigin</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustPackingSlipTrans</p></th>
<th><p>To Table: CustInvoicePackingSlipQuantityMatch</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SourceDocumentLine</p></td>
<td><p>PackingSlipSourceDocumentLine</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInvoiceTrans</p></th>
<th><p>To Table: CustInvoicePackingSlipQuantityMatch</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SourceDocumentLine</p></td>
<td><p>InvoiceSourceDocumentLine</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: InventTrans</p></th>
<th><p>To Table: CustInvoicePackingSlipQuantityMatch</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Qty</p></td>
<td><p>InventQuantity</p></td>
</tr>
</tbody>
</table>

  


