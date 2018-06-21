---
title: ReleaseUpdateDB60_Cust.updateSalesLine_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateSalesLine_BR Upgrade Script
ms:assetid: 53344d15-bc5b-48d1-ebe3-8127c6954971
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685575(v=AX.60)
ms:contentKeyID: 49708269
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateSalesLine\_BR Upgrade Script [AX 2012]


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
<td><p>updateSalesLine_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SalesLine_BR table records from the SalesLine table records.</p></td>
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
<td><p>SalesLine_BR</p></td>
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
<th><p>From Table: SalesLine</p></th>
<th><p>To Table: SalesLine_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SuframaDiscount_BR</p></td>
<td><p>SuframaDiscount_BR</p></td>
</tr>
<tr class="even">
<td><p>TaxServiceCode_BR</p></td>
<td><p>TaxServiceCode_BR</p></td>
</tr>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SalesLine</p></td>
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
<td><p>SalesLine_BR</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>SalesLine</p></td>
<td><p>SuframaDiscount_BR</p></td>
</tr>
<tr class="even">
<td><p>SalesLine</p></td>
<td><p>TaxServiceCode_BR</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

