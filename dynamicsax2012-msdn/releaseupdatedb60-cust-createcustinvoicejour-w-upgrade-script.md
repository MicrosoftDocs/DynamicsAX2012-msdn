---
title: ReleaseUpdateDB60_Cust.createCustInvoiceJour_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustInvoiceJour_W Upgrade Script
ms:assetid: 9763dddf-1089-0d09-bc62-f341fbc0e56d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686215(v=AX.60)
ms:contentKeyID: 49709919
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustInvoiceJour\_W Upgrade Script [AX 2012]


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
<td><p>createCustInvoiceJour_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country specific fields from &lt;c&gt;CustInvoiceJour&lt;/c&gt; table to &lt;c&gt;CustInvoiceJour_W&lt;/c&gt; table</p></td>
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
<td><p>CustInvoiceJour_W</p></td>
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
<th><p>To Table: CustInvoiceJour_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BankAccount_LV</p></td>
<td><p>BankAccount_W</p></td>
</tr>
<tr class="even">
<td><p>CompanyCurBankAccount_LV</p></td>
<td><p>CompanyCurBankAccount_W</p></td>
</tr>
<tr class="odd">
<td><p>CustBankAccount_LV</p></td>
<td><p>CustBankAccount_LV</p></td>
</tr>
<tr class="even">
<td><p>CustConsInvoice_JP</p></td>
<td><p>CustConsInvoice_JP</p></td>
</tr>
<tr class="odd">
<td><p>IntrastatAddValue_LV</p></td>
<td><p>IntrastatAddValue_LV</p></td>
</tr>
<tr class="even">
<td><p>InvoiceRegister_LT</p></td>
<td><p>InvoiceRegister_W</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceStatus_LT</p></td>
<td><p>InvoiceStatus_W</p></td>
</tr>
<tr class="even">
<td><p>NumberSequenceCode_LT</p></td>
<td><p>NumberSequenceCode_W</p></td>
</tr>
<tr class="odd">
<td><p>PrintBlankDate_LT</p></td>
<td><p>PrintBlankDate_W</p></td>
</tr>
<tr class="even">
<td><p>SalesDate_W</p></td>
<td><p>SalesDate_W</p></td>
</tr>
<tr class="odd">
<td><p>SumTaxWithhold_IN</p></td>
<td><p>SumTaxWithhold_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxReimbursementDoc_HU</p></td>
<td><p>TaxReimbursementDoc_HU</p></td>
</tr>
<tr class="odd">
<td><p>TaxWithholdAmount_IN</p></td>
<td><p>TaxWithholdAmount_IN</p></td>
</tr>
<tr class="even">
<td><p>UnitedVATInvoice_LT</p></td>
<td><p>UnitedVATInvoice_LT</p></td>
</tr>
<tr class="odd">
<td><p>VatSettled_HU</p></td>
<td><p>VatSettled_HU</p></td>
</tr>
<tr class="even">
<td><p>WhoIsAuthor_LT</p></td>
<td><p>WhoIsAuthor_LT</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

