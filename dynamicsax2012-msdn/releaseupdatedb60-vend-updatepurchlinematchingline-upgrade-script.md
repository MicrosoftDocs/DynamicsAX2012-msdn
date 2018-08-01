---
title: ReleaseUpdateDB60_Vend.updatePurchLineMatchingLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchLineMatchingLine Upgrade Script
ms:assetid: 53079fe9-7828-d7af-5ed1-0812dc72bf49
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685569(v=AX.60)
ms:contentKeyID: 49708263
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchLineMatchingLine Upgrade Script 


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
<td><p>updatePurchLineMatchingLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the RefTableId and RefRecId values in the VendInvoiceMatchingLine table to relate to the VendInvoiceInfoLine table.</p></td>
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
<td><p>VendInvoiceMatchingLine</p></td>
</tr>
</tbody>
</table>


## Remarks

In Microsoft Dynamics AX 2012, release invoices reside in the table hierarchy related to the VendInvoiceInfoTable table. In prior releases, invoices that ar ebeing posted resided in the PurchParmTable table. This method moves VendInvoiceMatchingLine records between the two hierarchies by setting reference fields appropriately. After the update, VendInvoiceMatchingLine records which were related to PurchParmLine records will relate to VendInvoiceInfoLine records to which the data was copied.

  


