---
title: ReleaseUpdateDB60_Vend.copyDuplicatePurchLineAsset Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.copyDuplicatePurchLineAsset Upgrade Script
ms:assetid: f28bf3a4-b5a6-9a60-e1e6-a81384bfec3a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737482(v=AX.60)
ms:contentKeyID: 49712176
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.copyDuplicatePurchLineAsset Upgrade Script 


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
<td><p>copyDuplicatePurchLineAsset</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from PurchParmLine_Asset table that is related to duplicate PurchParmLine to VendInvoiceInfoLine_Asset table.</p></td>
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
<td><p>PurchParmLine_Asset</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoLine_Asset</p></td>
</tr>
</tbody>
</table>


## Remarks

In Microsoft Dynamics AX 2012, release invoices reside in the table hierarchy that is related to the VendInvoiceInfoTable table. In prior releases, invoices that are being posted reside in the PurchParmTable table. This method is a helper method for the upgrade scripts and moves data between the two hierarchies.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchParmLine_Asset</p></th>
<th><p>To Table: VendInvoiceInfoLine_Asset</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


