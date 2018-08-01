---
title: ReleaseUpdateDB60_Cust.updateCustomsShippingBillTrans_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustomsShippingBillTrans_IN Upgrade Script
ms:assetid: beb07ff1-b3ae-30f5-71f5-2889d11752d2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686713(v=AX.60)
ms:contentKeyID: 49710911
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustomsShippingBillTrans\_IN Upgrade Script 


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
<td><p>updateCustomsShippingBillTrans_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CustomsShippingBillTrans_IN table. The record ID of the CustomsShippingBillNumberTable_IN record is now stored in place of the CustomsShippingBillNumber_IN field value.</p></td>
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
<td><p>CustomsShippingBillNumberTable_IN</p></td>
</tr>
<tr class="even">
<td><p>CustomsShippingBillTrans_IN</p></td>
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
<th><p>From Table: CustomsShippingBillNumberTable_IN</p></th>
<th><p>To Table: CustomsShippingBillTrans_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CustomsShippingBillNumberTable</p></td>
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
<td><p>CustomsShippingBillTrans_IN</p></td>
<td><p>CustomsShippingBillNumberTable</p></td>
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
<td><p>CustomsShippingBillTrans_IN</p></td>
<td><p>del_ShippingBillNumber</p></td>
</tr>
</tbody>
</table>

  


