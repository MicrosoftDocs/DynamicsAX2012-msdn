---
title: ReleaseUpdateDB60_Vend.updatePurchLineHistory Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchLineHistory Upgrade Script
ms:assetid: 04bb6a7c-88c8-b07c-5822-39331d4f3c01
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684705(v=AX.60)
ms:contentKeyID: 49706401
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchLineHistory Upgrade Script 


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
<td><p>updatePurchLineHistory</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the LineNumber value in the PurchLine table.</p></td>
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
<td><p>PurchLineHistory</p></td>
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
<th><p>From Table: PurchLine</p></th>
<th><p>To Table: PurchLineHistory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LineNumber</p></td>
<td><p>LineNumber</p></td>
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
<td><p>PurchLineHistory</p></td>
<td><p>LineNumber</p></td>
<td><p>TradeLineNumber</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
<td><p>LineNumber</p></td>
<td><p>TradeLineNumber</p></td>
</tr>
</tbody>
</table>

  


