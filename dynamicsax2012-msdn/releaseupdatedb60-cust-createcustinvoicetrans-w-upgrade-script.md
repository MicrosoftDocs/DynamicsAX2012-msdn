---
title: ReleaseUpdateDB60_Cust.createCustInvoiceTrans_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustInvoiceTrans_W Upgrade Script
ms:assetid: b18a05e0-b888-723a-c784-808546b2adf2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736904(v=AX.60)
ms:contentKeyID: 49710588
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustInvoiceTrans\_W Upgrade Script 


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
<td><p>createCustInvoiceTrans_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country specific fields from &lt;c&gt;CustInvoiceTrans&lt;/c&gt; table to &lt;c&gt;CustInvoiceTrans_W&lt;/c&gt; table</p></td>
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
<td><p>CustInvoiceTrans_W</p></td>
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
<th><p>To Table: CustInvoiceTrans_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CreditNoteInternalRef_PL</p></td>
<td><p>CreditNoteInternalRef_W</p></td>
</tr>
<tr class="even">
<td><p>PKWiUCode_PL</p></td>
<td><p>PKWiUCode_PL</p></td>
</tr>
<tr class="odd">
<td><p>RefReturnInvoiceTrans_W</p></td>
<td><p>RefReturnInvoiceTrans_W</p></td>
</tr>
<tr class="even">
<td><p>StatisticValue_LT</p></td>
<td><p>StatisticValue_LT</p></td>
</tr>
<tr class="odd">
<td><p>TaxReimbursement_HU</p></td>
<td><p>TaxReimbursement_HU</p></td>
</tr>
</tbody>
</table>

  


