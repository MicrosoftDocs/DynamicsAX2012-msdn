---
title: ReleaseUpdateDB60_Cust.updateSalesPackingSlipQuantityCorrection Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateSalesPackingSlipQuantityCorrection Upgrade Script
ms:assetid: 02c04466-2882-6bd6-d897-88a75940b9f0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684654(v=AX.60)
ms:contentKeyID: 49706351
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateSalesPackingSlipQuantityCorrection Upgrade Script 


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
<td><p>updateSalesPackingSlipQuantityCorrection</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the SalesPackingSlipQuantityCorrection table for corrected sales packing slips of open sales orders.</p></td>
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
<td><p>CustPackingSlipJour</p></td>
</tr>
<tr class="even">
<td><p>CustPackingSlipTrans</p></td>
</tr>
<tr class="odd">
<td><p>InventTrans</p></td>
</tr>
<tr class="even">
<td><p>InventTransOrigin</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
</tr>
<tr class="even">
<td><p>SalesPackingSlipQuantityCorrection</p></td>
</tr>
<tr class="odd">
<td><p>UnitOfMeasure</p></td>
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
<th><p>To Table: SalesPackingSlipQuantityCorrection</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>OriginalPackingSlipTrans</p></td>
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
<th><p>From Table: CustPackingSlipTrans</p></th>
<th><p>To Table: SalesPackingSlipQuantityCorrection</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CorrectingPackingSlipTrans</p></td>
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
<th><p>To Table: SalesPackingSlipQuantityCorrection</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Qty</p></td>
<td><p>InventoryQuantity</p></td>
</tr>
</tbody>
</table>

  


