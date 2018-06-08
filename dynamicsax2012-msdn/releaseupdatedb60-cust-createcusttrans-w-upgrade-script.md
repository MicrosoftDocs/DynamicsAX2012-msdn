---
title: ReleaseUpdateDB60_Cust.createCustTrans_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.createCustTrans_W Upgrade Script
ms:assetid: ed2dfc89-c0e0-d78f-67f6-8f1d54b84880
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719960(v=AX.60)
ms:contentKeyID: 49712032
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.createCustTrans\_W Upgrade Script 


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
<td><p>createCustTrans_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country specific fields from &lt;c&gt;CustTrans&lt;/c&gt; table to &lt;c&gt;CustTrans_W&lt;/c&gt; table</p></td>
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
<td><p>CustTrans</p></td>
</tr>
<tr class="even">
<td><p>CustTrans_W</p></td>
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
<th><p>From Table: CustTrans</p></th>
<th><p>To Table: CustTrans_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AdvancePayment_IN</p></td>
<td><p>AdvancePayment_IN</p></td>
</tr>
<tr class="even">
<td><p>CorrectReporting_RU</p></td>
<td><p>CorrectReporting_RU</p></td>
</tr>
<tr class="odd">
<td><p>DefaultDimensionReporting_RU</p></td>
<td><p>DefaultDimensionReporting_RU</p></td>
</tr>
<tr class="even">
<td><p>InvoicePostingType_RU</p></td>
<td><p>InvoicePostingType_RU</p></td>
</tr>
<tr class="odd">
<td><p>PrepaymentFactureId_W</p></td>
<td><p>PrepaymentFactureId_W</p></td>
</tr>
<tr class="even">
<td><p>RefVoucher_IN</p></td>
<td><p>RefVoucher_IN</p></td>
</tr>
<tr class="odd">
<td><p>RTax25Amortisation</p></td>
<td><p>RTax25Amortisation_RU</p></td>
</tr>
<tr class="even">
<td><p>TaxWithholdAmountOrigin_IN</p></td>
<td><p>TaxWithholdAmountOrigin_IN</p></td>
</tr>
<tr class="odd">
<td><p>TCSAmount_IN</p></td>
<td><p>TCSAmount_IN</p></td>
</tr>
<tr class="even">
<td><p>TDSAmount_IN</p></td>
<td><p>TDSAmount_IN</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

