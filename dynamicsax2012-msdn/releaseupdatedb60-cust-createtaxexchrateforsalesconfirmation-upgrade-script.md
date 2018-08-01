---
title: ReleaseUpdateDB60_Cust.createTaxExchRateForSalesConfirmation Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createTaxExchRateForSalesConfirmation Upgrade Script
ms:assetid: 016ffaea-8341-5a06-f1bb-2f7f20d44f60
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684626(v=AX.60)
ms:contentKeyID: 49706323
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createTaxExchRateForSalesConfirmation Upgrade Script 


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
<td><p>createTaxExchRateForSalesConfirmation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the SalesTaxTransactionExchangeRate table from the TaxJournalTrans table and the SalesParmTable table.</p></td>
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
<th><p>From Table: TaxJournalTrans</p></th>
<th><p>To Table: SalesTaxTransactionExchangeRate</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TransTableId</p></td>
<td><p>SourceTableId</p></td>
</tr>
<tr class="even">
<td><p>TransRecId</p></td>
<td><p>SourceRecordId</p></td>
</tr>
<tr class="odd">
<td><p>Del_ExchRateSales_W</p></td>
<td><p>SalesTaxExchangeRate</p></td>
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
<th><p>From Table: SalesParmTable</p></th>
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
<td><p>TaxJournalTrans</p></td>
<td><p>Del_ExchRateSales_W</p></td>
</tr>
</tbody>
</table>

  


