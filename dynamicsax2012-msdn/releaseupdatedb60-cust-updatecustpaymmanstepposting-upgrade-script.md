---
title: ReleaseUpdateDB60_Cust.updateCustPaymManStepPosting Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustPaymManStepPosting Upgrade Script
ms:assetid: 790d2f2e-c18a-ea8e-dc29-903f34f5c723
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719390(v=AX.60)
ms:contentKeyID: 49709181
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustPaymManStepPosting Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateCustPaymManStepPosting</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the CreditAccountNum and DebitAccountNum fields to the CreditLedgerDimension and DebitLedgerDimension fields, respectively, in the CustPaymManStepPosting table.</p></td>
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
<td><p>CustPaymManStepPosting</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account or dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustPaymManStepPosting</p></th>
<th><p>To Table: CustPaymManStepPosting</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CreditAccountNum</p></td>
<td><p>CreditLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>DebitAccountNum</p></td>
<td><p>DebitLedgerDimension</p></td>
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
<td><p>CustPaymManStepPosting</p></td>
<td><p>CreditLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>CustPaymManStepPosting</p></td>
<td><p>DebitLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
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
<td><p>CustPaymManStepPosting</p></td>
<td><p>CreditAccountNum</p></td>
</tr>
<tr class="even">
<td><p>CustPaymManStepPosting</p></td>
<td><p>DebitAccountNum</p></td>
</tr>
</tbody>
</table>

  


