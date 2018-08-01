---
title: ReleaseUpdateDB60_Cust.createCustInvoiceJour_PL Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustInvoiceJour_PL Upgrade Script
ms:assetid: 1f9a5107-e752-b613-22a9-738bb94201c0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684872(v=AX.60)
ms:contentKeyID: 49707071
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustInvoiceJour\_PL Upgrade Script 


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
<td><p>createCustInvoiceJour_PL</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates Poland country specific fields from &lt;c&gt;CustInvoiceJour&lt;/c&gt; table to &lt;c&gt;CustInvoiceJour_PL&lt;/c&gt; table</p></td>
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
<td><p>CustInvoiceJour_PL</p></td>
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
<th><p>To Table: CustInvoiceJour_PL</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FiscalDocDate_PL</p></td>
<td><p>FiscalDocDate_PL</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocState_PL</p></td>
<td><p>FiscalDocState_PL</p></td>
</tr>
<tr class="odd">
<td><p>FiscalInvoiceAccount_PL</p></td>
<td><p>FiscalInvoiceAccount_PL</p></td>
</tr>
<tr class="even">
<td><p>FiscalOrderAccount_PL</p></td>
<td><p>FiscalOrderAccount_PL</p></td>
</tr>
<tr class="odd">
<td><p>FiscalPrinterCode_PL</p></td>
<td><p>FiscalPrinterCode_PL</p></td>
</tr>
</tbody>
</table>

  


