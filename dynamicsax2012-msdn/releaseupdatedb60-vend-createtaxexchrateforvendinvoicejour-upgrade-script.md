---
title: ReleaseUpdateDB60_Vend.createTaxExchRateForVendInvoiceJour Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createTaxExchRateForVendInvoiceJour Upgrade Script
ms:assetid: 1420a410-fecd-6900-f9bb-8ce35c09f3fa
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718507(v=AX.60)
ms:contentKeyID: 49706790
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createTaxExchRateForVendInvoiceJour Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>createTaxExchRateForVendInvoiceJour</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the SalesTaxTransactionExchangeRate table from the VendInvoiceJour table and the TaxTrans table.</p></td>
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
<td><p>SalesTaxTransactionExchangeRate</p></td>
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
<th><p>From Table: VendInvoiceJour</p></th>
<th><p>To Table: SalesTaxTransactionExchangeRate</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Del_ExchRate_W</p></td>
<td><p>SalesTaxExchangeRate</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>SourceTableId</p></td>
</tr>
<tr class="odd">
<td><p>TableId</p></td>
<td><p>SourceTableId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TaxTrans</p></th>
<th><p>To Table: SalesTaxTransactionExchangeRate</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VatDueDate_W</p></td>
<td><p>DateOfVATRegister</p></td>
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
<td><p>SalesTaxTransactionExchangeRate</p></td>
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
<td><p>VendInvoiceJour</p></td>
<td><p>Del_ExchRate_W</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

