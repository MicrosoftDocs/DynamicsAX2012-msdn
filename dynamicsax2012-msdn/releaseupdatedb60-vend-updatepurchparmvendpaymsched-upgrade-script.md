---
title: ReleaseUpdateDB60_Vend.updatePurchParmVendPaymSched Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchParmVendPaymSched Upgrade Script
ms:assetid: 414881c8-99e2-1572-d3cb-b2890a821556
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718822(v=AX.60)
ms:contentKeyID: 49707865
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchParmVendPaymSched Upgrade Script [AX 2012]


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
<td><p>updatePurchParmVendPaymSched</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ExtTableId and ExtRecID values for the VendPaymSched table to relate to the VendInvoiceInoTable table.</p></td>
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
<td><p>VendPaymSched</p></td>
</tr>
</tbody>
</table>


## Remarks

In Microsoft Dynamics AX 2012, release invoices reside in the table hierarchy related to the VendInvoiceInfoTable table. In prior releases, invoices that are being posted resided in the PurchParmTable table. This method moves VendPaymSched records between the two hierarchies by setting reference fields appropriately. After the update, VendPaymSched records that were related to PurchParmTable records are related to VendInvoiceInfoTable records to which the data was copied.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

