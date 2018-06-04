---
title: ReleaseUpdateDB60_Cust.updateCustInvoiceForExportSales Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustInvoiceForExportSales Upgrade Script
ms:assetid: f0d20b6b-ce58-990d-b3db-de0b11f5249c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737439(v=AX.60)
ms:contentKeyID: 49712134
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustInvoiceForExportSales Upgrade Script 


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
<td><p>updateCustInvoiceForExportSales</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method creates an ExportSalesOrder, ExportSalesInvoice, ExportSalesInvoiceLineDomesticTaxGroup, and ExportSalesInvoiceDomesticTaxVoucher record for export sales from the SalesTable, CustInvoiceJour, CustInvoiceTrans, LedgerJournalTrans, and LedgerJournalTable records.</p></td>
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
<td><p>SALESTABLE</p></td>
</tr>
<tr class="even">
<td><p>EXPORTSALESORDER</p></td>
</tr>
<tr class="odd">
<td><p>CUSTINVOICEJOUR</p></td>
</tr>
<tr class="even">
<td><p>EXPORTSALESINVOICE</p></td>
</tr>
<tr class="odd">
<td><p>CUSTINVOICETRANS</p></td>
</tr>
<tr class="even">
<td><p>EXPORTSALESINVOICELINEDOMESTICTAXGROUP</p></td>
</tr>
<tr class="odd">
<td><p>EXPORTSALESINVOICEDOMESTICTAXVOUCHER</p></td>
</tr>
<tr class="even">
<td><p>LEDGERJOURNALTRANS</p></td>
</tr>
<tr class="odd">
<td><p>LEDGERJOURNALTABLE</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

