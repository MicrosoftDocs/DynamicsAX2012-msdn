---
title: ReleaseUpdateDB60_Cust.updateCustInvPackingSlipQtyMatchItemReq Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustInvPackingSlipQtyMatchItemReq Upgrade Script
ms:assetid: 434173c1-d9b9-5462-a011-611965d19c40
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718867(v=AX.60)
ms:contentKeyID: 49707911
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustInvPackingSlipQtyMatchItemReq Upgrade Script 


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
<td><p>updateCustInvPackingSlipQtyMatchItemReq</p></td>
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
<td><p>CustInvoicePackingSlipQuantityMatch</p></td>
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
<td><p>ProjInvoiceItem</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceJour</p></td>
</tr>
<tr class="even">
<td><p>ProjItemTrans</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
</tr>
<tr class="even">
<td><p>SourceDocumentHeader</p></td>
</tr>
<tr class="odd">
<td><p>SourceDocumentLine</p></td>
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
<th><p>From Table: ProjInvoiceItem</p></th>
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

  


