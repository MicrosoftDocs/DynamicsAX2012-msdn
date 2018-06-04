---
title: ReleaseUpdateDB60_Cust.createCustInvoiceTrans_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustInvoiceTrans_RU Upgrade Script
ms:assetid: 151ab244-c7d0-c60f-cd10-091686c0a8d9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718530(v=AX.60)
ms:contentKeyID: 49706811
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustInvoiceTrans\_RU Upgrade Script 


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
<td><p>createCustInvoiceTrans_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates Russia country specific fields from &lt;c&gt;CustInvoiceTrans&lt;/c&gt; table to &lt;c&gt;CustInvoiceTrans_RU&lt;/c&gt; table</p></td>
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
<td><p>CustInvoiceTrans</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceTrans_RU</p></td>
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
<th><p>From Table: CustInvoiceTrans</p></th>
<th><p>To Table: CustInvoiceTrans_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AssetId_RU</p></td>
<td><p>AssetId_RU</p></td>
</tr>
<tr class="even">
<td><p>CountryRegionName_RU</p></td>
<td><p>CountryRegionName_RU</p></td>
</tr>
<tr class="odd">
<td><p>ExciseAmount_RU</p></td>
<td><p>ExciseAmount_RU</p></td>
</tr>
<tr class="even">
<td><p>ExciseAmountMST_RU</p></td>
<td><p>ExciseAmountMST_RU</p></td>
</tr>
<tr class="odd">
<td><p>ExciseValue_RU</p></td>
<td><p>ExciseValue_RU</p></td>
</tr>
<tr class="even">
<td><p>FacturedFully_RU</p></td>
<td><p>FacturedFully_RU</p></td>
</tr>
<tr class="odd">
<td><p>FacturedQty_RU</p></td>
<td><p>FacturedQty_RU</p></td>
</tr>
<tr class="even">
<td><p>InventTransIdDelivery_RU</p></td>
<td><p>InventTransIdDelivery_RU</p></td>
</tr>
<tr class="odd">
<td><p>InventTransIdTransit_RU</p></td>
<td><p>InventTransIdTransit_RU</p></td>
</tr>
<tr class="even">
<td><p>VATAmount_RU</p></td>
<td><p>VATAmount_RU</p></td>
</tr>
<tr class="odd">
<td><p>VATAmountMST_RU</p></td>
<td><p>VATAmountMST_RU</p></td>
</tr>
<tr class="even">
<td><p>VATValue_RU</p></td>
<td><p>VATValue_RU</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

