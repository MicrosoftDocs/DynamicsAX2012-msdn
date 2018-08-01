---
title: ReleaseUpdateDB60_Cust.updateVendTablePaymTransCodes Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateVendTablePaymTransCodes Upgrade Script
ms:assetid: a957aa35-b3d6-5f94-2f3a-0d4a36dc2517
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686427(v=AX.60)
ms:contentKeyID: 49710383
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateVendTablePaymTransCodes Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateVendTablePaymTransCodes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the payment transaction codes information for the VendTable table.</p></td>
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
<td><p>Bank</p></td>
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
<td><p>LvPaymTransCodes</p></td>
</tr>
<tr class="even">
<td><p>VendTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The payment transaction codes information used to be stored as a textual string in the old fields in AX4 and AX5. The new data model is a field that now holds a surrogate foreign key reference to the new LvPaymTransCodes table.

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
<td><p>LvPaymTransCodes</p></td>
<td><p>Description</p></td>
<td><p>Description</p></td>
</tr>
<tr class="even">
<td><p>LvPaymTransCodes</p></td>
<td><p>PaymTransCode</p></td>
<td><p>LvPaymCode</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: VendTable</p></th>
<th><p>New Table Name: VendTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>PaymCode_LV</p></td>
<td><p>PaymTransCode</p></td>
</tr>
</tbody>
</table>

  


