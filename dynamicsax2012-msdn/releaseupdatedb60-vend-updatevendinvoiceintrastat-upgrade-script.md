---
title: ReleaseUpdateDB60_Vend.updateVendInvoiceIntrastat Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendInvoiceIntrastat Upgrade Script
ms:assetid: a778fcc5-e450-3de2-4e31-0828e17f03eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686357(v=AX.60)
ms:contentKeyID: 49710313
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendInvoiceIntrastat Upgrade Script 


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
<td><p>updateVendInvoiceIntrastat</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the vendInvoiceJour field on the VendInvoiceIntrastat table by looking for matching voucher and transDate fields in the VendInvoiceJour table.</p></td>
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
<td><p>VendInvoiceIntrastat</p></td>
</tr>
</tbody>
</table>


## Remarks

The data model for the table is changed. The new vendInvoiceJour field is the foreign key to the VendInvoiceJour table and is updated by looking for matching transDate and voucher fields. If the DEL\_Reversed field is set, a new record needs to be created as per the new data model to handle the reversal and cancellation scenario.

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
<td><p>VendInvoiceIntrastat</p></td>
<td><p>VendInvoiceJour</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VendInvoiceIntrastat</p></td>
<td><p>DEL_StatTriangularDeal</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceIntrastat</p></td>
<td><p>DEL_Reversed</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceIntrastat</p></td>
<td><p>DEL_TransDateReversed</p></td>
</tr>
</tbody>
</table>

  


