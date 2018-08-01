---
title: ReleaseUpdateDB60_Cust.createCustInvoiceJour_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustInvoiceJour_RU Upgrade Script
ms:assetid: 44909e5d-cb9a-e110-dd20-50d6dd8ebe9d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718907(v=AX.60)
ms:contentKeyID: 49707957
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustInvoiceJour\_RU Upgrade Script 


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
<td><p>createCustInvoiceJour_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates Russia country specific fields from &lt;c&gt;CustInvoiceJour&lt;/c&gt; table to &lt;c&gt;CustInvoiceJour_RU&lt;/c&gt; table</p></td>
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
<td><p>CustInvoiceJour_RU</p></td>
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
<th><p>To Table: CustInvoiceJour_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_AttorneyDate_RU</p></td>
<td><p>AttorneyDate_RU</p></td>
</tr>
<tr class="even">
<td><p>DEL_AttorneyId_RU</p></td>
<td><p>AttorneyId_RU</p></td>
</tr>
<tr class="odd">
<td><p>DEL_AttorneyIssuedName_RU</p></td>
<td><p>AttorneyIssuedName_RU</p></td>
</tr>
<tr class="even">
<td><p>DEL_ConsigneeAccount_RU</p></td>
<td><p>ConsigneeAccount_RU</p></td>
</tr>
<tr class="odd">
<td><p>DEL_ConsignorAccount_RU</p></td>
<td><p>ConsignorAccount_RU</p></td>
</tr>
<tr class="even">
<td><p>DEL_Correct_RU</p></td>
<td><p>Correct_RU</p></td>
</tr>
<tr class="odd">
<td><p>DEL_CorrectedInvoiceDate_RU</p></td>
<td><p>CorrectedInvoiceDate_RU</p></td>
</tr>
<tr class="even">
<td><p>DEL_CorrectedInvoiceId_RU</p></td>
<td><p>CorrectedInvoiceId_RU</p></td>
</tr>
<tr class="odd">
<td><p>DEL_FacturedFully_RU</p></td>
<td><p>FacturedFully_RU</p></td>
</tr>
<tr class="even">
<td><p>DEL_InventOwnerId_RU</p></td>
<td><p>InventOwnerId_RU</p></td>
</tr>
<tr class="odd">
<td><p>DEL_InventProfileType_RU</p></td>
<td><p>InventProfileType_RU</p></td>
</tr>
<tr class="even">
<td><p>DEL_InvoicePostingType_RU</p></td>
<td><p>InvoicePostingType_RU</p></td>
</tr>
<tr class="odd">
<td><p>DEL_NonRealRevenue_RU</p></td>
<td><p>NonRealRevenue_RU</p></td>
</tr>
<tr class="even">
<td><p>DEL_PrintStandardCurrency_RU</p></td>
<td><p>PrintStandardCurrency_RU</p></td>
</tr>
<tr class="odd">
<td><p>DEL_SettleVoucher_RU</p></td>
<td><p>SettleVoucher_RU</p></td>
</tr>
<tr class="even">
<td><p>DEL_VATOnPayment_RU</p></td>
<td><p>VATOnPayment_RU</p></td>
</tr>
</tbody>
</table>

  


