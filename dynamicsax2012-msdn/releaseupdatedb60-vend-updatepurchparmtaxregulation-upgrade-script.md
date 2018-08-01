---
title: ReleaseUpdateDB60_Vend.updatePurchParmTaxRegulation Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchParmTaxRegulation Upgrade Script
ms:assetid: da93f825-7d60-fcf7-b21b-2d0e3f3feaf8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737174(v=AX.60)
ms:contentKeyID: 49711617
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchParmTaxRegulation Upgrade Script 


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
<td><p>updatePurchParmTaxRegulation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the HeadingTableId and HeadingRecID values for the TaxWorkRegulation table to relate to the VendInvoiceInoTable table.</p></td>
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
<td><p>TaxWorkRegulation</p></td>
</tr>
</tbody>
</table>


## Remarks

In Microsoft Dynamics AX 2012 release invoices reside in the table hierarchy related to VendInvoiceInfoTable table. In prior releases, invoices that are being posted resided in the PurchParmTable table. This method moves TaxWorkRegulation records between the two hierarchies by setting reference fields appropriately. After the update, TaxWorkRegulation records that were related to PurchParmTable records are related to VendInvoiceInfoTable records to which the data was copied.

  


