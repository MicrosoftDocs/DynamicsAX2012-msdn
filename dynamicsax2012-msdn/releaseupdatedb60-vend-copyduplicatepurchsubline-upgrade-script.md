---
title: ReleaseUpdateDB60_Vend.copyDuplicatePurchSubLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.copyDuplicatePurchSubLine Upgrade Script
ms:assetid: ecc78b68-a293-0bd2-759c-0ff6d8efbebe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719923(v=AX.60)
ms:contentKeyID: 49711995
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.copyDuplicatePurchSubLine Upgrade Script [AX 2012]


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
<td><p>copyDuplicatePurchSubLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the PurchParmSubLine table, which is related to duplicate PurchParmLine data, to the VendInvoiceInfoSubLine table.</p></td>
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
<td><p>PurchParmSubLine</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoSubLine</p></td>
</tr>
</tbody>
</table>


## Remarks

In Microsoft Dynamics AX 2012, release invoices reside in the table hierarchy that is related to the VendInvoiceInfoTable table. In prior releases, invoices that are being posted reside in the PurchParmTable table. This method is a helper method for upgrade scripts that move data between the two hierarchies.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchParmSubLine</p></th>
<th><p>To Table: VendInvoiceInfoSubLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

