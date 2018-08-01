---
title: ReleaseUpdateDB60_Vend.updatePurchParmSubMarkupTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchParmSubMarkupTrans Upgrade Script
ms:assetid: b60d1e86-0494-1fa1-2a9e-2d437828bf92
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737010(v=AX.60)
ms:contentKeyID: 49710691
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchParmSubMarkupTrans Upgrade Script 


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
<td><p>updatePurchParmSubMarkupTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TransTableID and TransRecID values for the MarkupTrans table to be related to the VendInvoiceInoSubTable table.</p></td>
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

In 6.0 release invoices reside in table hierarchy related to VendInvoiceInfoTable, while in prior releases invoices being posted resided in PurchParmTable. This method moves MarkupTrans records between the two hierarchies, by setting reference fields appropriately. After the update MarkupTrans records which were related to PurchParmSubTable record are related to VendInvoiceInfoSubTable record to which the data was copied.

  


