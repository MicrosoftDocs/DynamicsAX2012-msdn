---
title: ReleaseUpdateDB60_Vend.copyPurchParmSubTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.copyPurchParmSubTable Upgrade Script
ms:assetid: 2c376b07-7b48-3d0e-85bf-4b2eccc776de
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735961(v=AX.60)
ms:contentKeyID: 49707379
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.copyPurchParmSubTable Upgrade Script 


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
<td><p>copyPurchParmSubTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the PurchParmSubTable table to the VendInvoiceInfoSubTable table.</p></td>
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
<td><p>PurchParmSubTable</p></td>
</tr>
<tr class="even">
<td><p>PurchParmTable</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoSubTable</p></td>
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
<th><p>From Table: PurchParmSubTable</p></th>
<th><p>To Table: VendInvoiceInfoSubTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OrigPurchId</p></td>
<td><p>OrigPurchId</p></td>
</tr>
<tr class="even">
<td><p>ParmId</p></td>
<td><p>ParmId</p></td>
</tr>
<tr class="odd">
<td><p>PurchName</p></td>
<td><p>PurchName</p></td>
</tr>
<tr class="even">
<td><p>TableRefId</p></td>
<td><p>TableRefId</p></td>
</tr>
</tbody>
</table>

  


