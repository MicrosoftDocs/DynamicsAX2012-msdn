---
title: ReleaseUpdateDB60_EMS.updateEMSFlow Upgrade Script
TOCTitle: ReleaseUpdateDB60_EMS.updateEMSFlow Upgrade Script
ms:assetid: c37254b8-0030-4996-89a2-b49a9fcadc77
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686834(v=AX.60)
ms:contentKeyID: 49711032
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EMS.updateEMSFlow Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_EMS</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEMSFlow</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the EMSFlow table.</p></td>
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
<td><p>Environment</p></td>
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
<td><p>EMSFlow</p></td>
</tr>
<tr class="even">
<td><p>EMSInvoiceRegisterFlowRelation</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
</tr>
<tr class="even">
<td><p>EMSPurchOrderFlowRelation</p></td>
</tr>
<tr class="odd">
<td><p>LedgerJournalTrans</p></td>
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
<td><p>EMSFlow</p></td>
<td><p>TransactionCurrencyAmount</p></td>
<td><p>AmountCur</p></td>
</tr>
<tr class="even">
<td><p>EMSFlow</p></td>
<td><p>AccountingCurrencyAmount</p></td>
<td><p>AmountMST</p></td>
</tr>
<tr class="odd">
<td><p>EMSFlow</p></td>
<td><p>TransactionCurrency</p></td>
<td><p>CurrencyCode</p></td>
</tr>
<tr class="even">
<td><p>EMSFlow</p></td>
<td><p>TransDate</p></td>
<td><p>TransDate</p></td>
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
<td><p>EMSFlow</p></td>
<td><p>AmountPercentage</p></td>
</tr>
</tbody>
</table>

  


