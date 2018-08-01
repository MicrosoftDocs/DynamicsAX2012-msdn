﻿---
title: ReleaseUpdateDB41_Cust.updateDeliveryDateControlType Upgrade Script
TOCTitle: ReleaseUpdateDB41_Cust.updateDeliveryDateControlType Upgrade Script
ms:assetid: 08c133b0-ece8-928a-69d7-0c1b8aca7282
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684794(v=AX.60)
ms:contentKeyID: 49706489
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Cust.updateDeliveryDateControlType Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateDeliveryDateControlType</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the DeliveryDateControlType value to SalesLeadTime value if the DEL_DeliveryDateControl value is true.</p></td>
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
<td><p>SalesLine</p></td>
</tr>
<tr class="even">
<td><p>SalesParameters</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationLine</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
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
<td><p>SalesParameters</p></td>
<td><p>DeliveryDateControlType</p></td>
<td><p>SalesDeliveryDateControlType</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>DeliveryDateControlType</p></td>
<td><p>SalesDeliveryDateControlType</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
<td><p>DeliveryDateControlType</p></td>
<td><p>SalesDeliveryDateControlType</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryDateControlType</p></td>
<td><p>SalesDeliveryDateControlType</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationLine</p></td>
<td><p>DeliveryDateControlType</p></td>
<td><p>SalesDeliveryDateControlType</p></td>
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
<td><p>SalesParameters</p></td>
<td><p>del_DeliveryDateControl</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>del_DeliveryDateControl</p></td>
</tr>
<tr class="odd">
<td><p>SalesLine</p></td>
<td><p>del_DeliveryDateControl</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
<td><p>del_DeliveryDateControl</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationLine</p></td>
<td><p>del_DeliveryDateControl</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

