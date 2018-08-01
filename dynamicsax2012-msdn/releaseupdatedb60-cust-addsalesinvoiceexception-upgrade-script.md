---
title: ReleaseUpdateDB60_Cust.addSalesInvoiceException Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.addSalesInvoiceException Upgrade Script
ms:assetid: 4791b74c-6c43-0b81-0df5-6978cf447fba
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718976(v=AX.60)
ms:contentKeyID: 49708036
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.addSalesInvoiceException Upgrade Script 


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
<td><p>addSalesInvoiceException</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Adds an exception to not copy the SalesInvoiceTmp and FreeTextInvoiceTmp tables to AX6.2.</p></td>
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
<td><p>SalesInvoiceTmp</p></td>
</tr>
<tr class="even">
<td><p>FreeTextInvoiceTmp</p></td>
</tr>
</tbody>
</table>


## Remarks

The SalesInvoiceTmp and FreeTextInvoiceTmp tables are used by sales invoice and free text invoice reports and they do not contain data so they should not be copied to the new version.

  


