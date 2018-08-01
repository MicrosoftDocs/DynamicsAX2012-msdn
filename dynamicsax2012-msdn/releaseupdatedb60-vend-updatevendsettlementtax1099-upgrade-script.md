---
title: ReleaseUpdateDB60_Vend.updateVendSettlementTax1099 Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendSettlementTax1099 Upgrade Script
ms:assetid: 01d8c2a0-a854-5452-851e-b9ed0d93888c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684636(v=AX.60)
ms:contentKeyID: 49706333
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendSettlementTax1099 Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateVendSettlementTax1099</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the VendSettlementTax1099 table to have a foreign key for the Tax1099Fields table in the same company.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>VendSettlementTax1099</p></td>
</tr>
</tbody>
</table>


## Remarks

This is necessary to repair data left in an invalid state after posting inter-company settlements for 1099 vendors.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendSettlementTax1099</p></th>
<th><p>To Table: VendSettlementTax1099</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tax1099Fields</p></td>
<td><p>Tax1099Fields</p></td>
</tr>
</tbody>
</table>

  


