---
title: ReleaseUpdateDB60_Ledger.updateInventProfile_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateInventProfile_RU Upgrade Script
ms:assetid: 453cf454-ea4d-5b59-e257-3c50f3e4ff66
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718929(v=AX.60)
ms:contentKeyID: 49707961
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateInventProfile\_RU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateInventProfile_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the PostingProfile_RU field in the LedgerCov table with the information from a related table.</p></td>
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
<td><p>SalesTable</p></td>
</tr>
<tr class="even">
<td><p>PurchTable</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceTable</p></td>
</tr>
<tr class="even">
<td><p>CustTransOpen</p></td>
</tr>
<tr class="odd">
<td><p>VendTransOpen</p></td>
</tr>
<tr class="even">
<td><p>ForecastPurch</p></td>
</tr>
<tr class="odd">
<td><p>ForecastSales</p></td>
</tr>
</tbody>
</table>


## Remarks

In the case the CustTransOpen, VendTransOpen, ForecastPurch, and ForecastSales tables the value of the PostingProfile\_RU field not filled from the related table but from multiple related tables or from a parameter table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

