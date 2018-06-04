---
title: ReleaseUpdateDB60_Vend.createVendInvoiceInfoLine_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createVendInvoiceInfoLine_W Upgrade Script
ms:assetid: 46d4cd3e-0eec-d2b4-256d-38ed42c5756d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718972(v=AX.60)
ms:contentKeyID: 49708006
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createVendInvoiceInfoLine\_W Upgrade Script 


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
<td><p>createVendInvoiceInfoLine_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country specific fields from &lt;c&gt;VendInvoiceInfoLine&lt;/c&gt; table to &lt;c&gt;VendInvoiceInfoLine_W&lt;/c&gt; table</p></td>
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
<td><p>VendInvoiceInfoLine</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoLine_W</p></td>
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
<th><p>From Table: VendInvoiceInfoLine</p></th>
<th><p>To Table: VendInvoiceInfoLine_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AssessableValue_IN</p></td>
<td><p>AssessableValue_IN</p></td>
</tr>
<tr class="even">
<td><p>CFOPTable_BR</p></td>
<td><p>CFOPTable_BR</p></td>
</tr>
<tr class="odd">
<td><p>CountryRegionName_RU</p></td>
<td><p>CountryRegionName_RU</p></td>
</tr>
<tr class="even">
<td><p>CustomsBillOfEntryNumberTable_IN</p></td>
<td><p>CustomsBillOfEntryNumberTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>CustomsImportInvoiceNumberTable_IN</p></td>
<td><p>CustomsImportInvoiceNumberTable_IN</p></td>
</tr>
<tr class="even">
<td><p>CustomsInvoiceRegnRecId_IN</p></td>
<td><p>CustomsInvoiceRegnRecId_IN</p></td>
</tr>
<tr class="odd">
<td><p>DeviationQty_RU</p></td>
<td><p>DeviationQty_RU</p></td>
</tr>
<tr class="even">
<td><p>InventProfileType_RU</p></td>
<td><p>InventProfileType_RU</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceGTDId_RU</p></td>
<td><p>InvoiceGTDId_RU</p></td>
</tr>
<tr class="even">
<td><p>LedgerDimension_RU</p></td>
<td><p>LedgerDimension_RU</p></td>
</tr>
<tr class="odd">
<td><p>MarkupCode_RU</p></td>
<td><p>MarkupCode_RU</p></td>
</tr>
<tr class="even">
<td><p>MaximumRetailPrice_IN</p></td>
<td><p>MaximumRetailPrice_IN</p></td>
</tr>
<tr class="odd">
<td><p>PostingProfile_RU</p></td>
<td><p>PostingProfile_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxServiceCode_BR</p></td>
<td><p>TaxServiceCode_BR</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

