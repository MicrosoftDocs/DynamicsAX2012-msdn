---
title: ReleaseUpdateDB60_Vend.updatePurchParmMarkupTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchParmMarkupTrans Upgrade Script
ms:assetid: f32b7de4-da3c-9110-95e0-1a57ca8c5486
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737502(v=AX.60)
ms:contentKeyID: 49712196
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchParmMarkupTrans Upgrade Script 


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
<td><p>updatePurchParmMarkupTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the HeadingTableId and HeadingRecId values in the MarkupTrans table to relate to the VendInvoiceInoTable table.</p></td>
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
<td><p>MarkupTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

In Microsoft Dynamics AX 2012 release invoices reside in the table hierarchy related to the VendInvoiceInfoTable table. In prior releases, invoices that are being posted resided in the PurchParmTable table. This method moves MarkupTrans records between the two hierarchies by appropriately setting reference fields. After the update, MarkupTrans records that were related to PurchParmTable records are related to VendInvoiceInfoTable records to which the data was copied.

  


