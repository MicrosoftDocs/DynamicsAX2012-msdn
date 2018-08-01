---
title: ReleaseUpdateDB41_Invent.updateDeliveryDateControlType Upgrade Script
TOCTitle: ReleaseUpdateDB41_Invent.updateDeliveryDateControlType Upgrade Script
ms:assetid: c55519b9-1425-4dcf-1720-22e638911220
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719515(v=AX.60)
ms:contentKeyID: 49711083
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Invent.updateDeliveryDateControlType Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateDeliveryDateControlType</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the DeliveryDateControlType field to SalesLeadTime when the DEL_DeliveryDateControl field is set to true.</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>InventTransferLine</p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
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
<td><p>InventTransferTable</p></td>
<td><p>DeliveryDateControlType</p></td>
<td><p>DeliveryDateControlType</p></td>
</tr>
<tr class="even">
<td><p>InventTransferLine</p></td>
<td><p>DeliveryDateControlType</p></td>
<td><p>DeliveryDateControlType</p></td>
</tr>
</tbody>
</table>

  


