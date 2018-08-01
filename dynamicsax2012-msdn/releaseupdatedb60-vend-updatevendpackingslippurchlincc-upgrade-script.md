---
title: ReleaseUpdateDB60_Vend.updateVendPackingSlipPurchLinCC Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendPackingSlipPurchLinCC Upgrade Script
ms:assetid: b9129460-652a-5c42-f832-10e8a15988f7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737102(v=AX.60)
ms:contentKeyID: 49710784
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendPackingSlipPurchLinCC Upgrade Script [AX 2012]


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
<td><p>updateVendPackingSlipPurchLinCC</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the VendPackingSlipPurchLink table with the new relation to the VendPackingSlipJour table based on the RecId field.</p></td>
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
<td><p>VendPackingSlipJour</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipPurchLink</p></td>
</tr>
</tbody>
</table>


## Remarks

The old relation that was based on an alternate key is deleted.

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
<td><p>VendPackingSlipPurchLink</p></td>
<td><p>VendPackingSlipJour</p></td>
<td><p>VendPackingSlipJourRecId</p></td>
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
<td><p>VendPackingSlipPurchLink</p></td>
<td><p>PurchId</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipPurchLink</p></td>
<td><p>ParmId</p></td>
</tr>
<tr class="odd">
<td><p>VendPackingSlipPurchLink</p></td>
<td><p>InternalPackingSlipId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

