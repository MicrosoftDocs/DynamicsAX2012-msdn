---
title: ReleaseUpdateDB60_Cust.createCustInvoiceJour_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustInvoiceJour_BR Upgrade Script
ms:assetid: 88b096a1-ac12-dd77-d3c9-7d2150a0389e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736370(v=AX.60)
ms:contentKeyID: 49709560
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustInvoiceJour\_BR Upgrade Script [AX 2012]


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
<td><p>createCustInvoiceJour_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates Brazil country specific fields from &lt;c&gt;CustInvoiceJour&lt;/c&gt; table to &lt;c&gt;CustInvoiceJour_BR&lt;/c&gt; table</p></td>
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
<td><p>CustInvoiceJour</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour_BR</p></td>
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
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: CustInvoiceJour_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustFinalUser</p></td>
<td><p>CustFinalUser_BR</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>FiscalDocumentType_BR</p></td>
</tr>
<tr class="odd">
<td><p>FiscalEstablishment_BR</p></td>
<td><p>FiscalEstablishment_BR</p></td>
</tr>
<tr class="even">
<td><p>SalesPurchOperationType_BR</p></td>
<td><p>SalesPurchOperationType_BR</p></td>
</tr>
<tr class="odd">
<td><p>ServiceCodeOnDlvAddress_BR</p></td>
<td><p>ServiceCodeOnDlvAddress_BR</p></td>
</tr>
<tr class="even">
<td><p>TransitControlVoucher</p></td>
<td><p>TransitControlVoucher_BR</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

