---
title: ReleaseUpdateDB60_Cust.updateCustInvoiceLine_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustInvoiceLine_RU Upgrade Script
ms:assetid: ebb09dd9-ca3b-8f6e-8fbd-c5ef80d311ea
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719900(v=AX.60)
ms:contentKeyID: 49711972
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustInvoiceLine\_RU Upgrade Script 


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
<td><p>updateCustInvoiceLine_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Moves the Qty_RU and PriceUnit_RU fields of the CustInvoiceLine table to new system fields.</p></td>
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
<td><p>CustInvoiceLine</p></td>
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
<th><p>From Table: CustInvoiceLine</p></th>
<th><p>To Table: CustInvoiceLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Qty_RU</p></td>
<td><p>Quantity</p></td>
</tr>
<tr class="even">
<td><p>PriceUnit_RU</p></td>
<td><p>UnitPrice</p></td>
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
<td><p>CustInvoiceLine</p></td>
<td><p>Qty_RU</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceLine</p></td>
<td><p>PriceUnit_RU</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

