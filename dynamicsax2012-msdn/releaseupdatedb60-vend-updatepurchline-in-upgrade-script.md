---
title: ReleaseUpdateDB60_Vend.updatePurchLine_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchLine_IN Upgrade Script
ms:assetid: f8dc6be7-610a-82f3-0bdc-a256b5b5ab6a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720046(v=AX.60)
ms:contentKeyID: 49712352
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchLine\_IN Upgrade Script 


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
<td><p>updatePurchLine_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the PurchLine table. The record IDs of the CustomsTariffCodeTable_IN, ExciseTariffCodes_IN, and ServiceCodeTable_IN tables are now stored in place of the CustomsTariffCode_IN, ExciseTariffCode_IN, and ServiceCode_IN field values.</p></td>
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
<td><p>PurchLine</p></td>
</tr>
<tr class="even">
<td><p>CustomsTariffCodeTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>ExciseTariffCodes_IN</p></td>
</tr>
<tr class="even">
<td><p>ServiceCodeTable_IN</p></td>
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
<td><p>PurchLine</p></td>
<td><p>del_CustomsTariffCode_IN</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
<td><p>del_ExciseTariffCode_IN</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
<td><p>del_ServiceCode_IN</p></td>
</tr>
</tbody>
</table>

  


