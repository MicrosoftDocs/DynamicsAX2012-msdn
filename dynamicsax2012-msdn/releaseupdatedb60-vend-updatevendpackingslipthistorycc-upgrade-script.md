---
title: ReleaseUpdateDB60_Vend.updateVendPackingSlipTHistoryCC Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendPackingSlipTHistoryCC Upgrade Script
ms:assetid: 36e8831a-5195-8ceb-fe77-9e392c43e0a8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685176(v=AX.60)
ms:contentKeyID: 49707629
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendPackingSlipTHistoryCC Upgrade Script [AX 2012]


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
<td><p>updateVendPackingSlipTHistoryCC</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the VendPackingSlipTransHistory table by using the VendPackingSlipTrans table. The valid time state of the table is initialized from the VersionDateTime field on the VendPackingSlipVersion table.</p></td>
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
<td><p>VendPackingSlipTrans</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipTransHistory</p></td>
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
<th><p>From Table: VendPackingSlipTrans</p></th>
<th><p>To Table: VendPackingSlipTransHistory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Qty</p></td>
<td><p>Qty</p></td>
</tr>
<tr class="even">
<td><p>Remain</p></td>
<td><p>Remain</p></td>
</tr>
<tr class="odd">
<td><p>ValueMST</p></td>
<td><p>ValueMST</p></td>
</tr>
<tr class="even">
<td><p>RemainInvent</p></td>
<td><p>RemainInvent</p></td>
</tr>
<tr class="odd">
<td><p>InventQty</p></td>
<td><p>InventQty</p></td>
</tr>
<tr class="even">
<td><p>ReasonTableRef</p></td>
<td><p>ReasonTableRef</p></td>
</tr>
<tr class="odd">
<td><p>Weight</p></td>
<td><p>Weight</p></td>
</tr>
</tbody>
</table>


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
<td><p>VendPackingSlipTransHistory</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>VendPackingSlipTrans</p></td>
<td><p>PurchId</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipTrans</p></td>
<td><p>Qty</p></td>
</tr>
<tr class="odd">
<td><p>VendPackingSlipTrans</p></td>
<td><p>Remain</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipTrans</p></td>
<td><p>ValueMST</p></td>
</tr>
<tr class="odd">
<td><p>VendPackingSlipTrans</p></td>
<td><p>RemainInvent</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipTrans</p></td>
<td><p>InventQty</p></td>
</tr>
<tr class="odd">
<td><p>VendPackingSlipTrans</p></td>
<td><p>ReasonTableRef</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipTrans</p></td>
<td><p>Weight</p></td>
</tr>
<tr class="odd">
<td><p>VendPackingSlipTrans</p></td>
<td><p>InternalPackingSlipId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

