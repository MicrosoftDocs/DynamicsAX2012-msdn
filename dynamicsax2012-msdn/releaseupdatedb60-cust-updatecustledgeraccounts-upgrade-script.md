---
title: ReleaseUpdateDB60_Cust.updateCustLedgerAccounts Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustLedgerAccounts Upgrade Script
ms:assetid: 9cb771df-3eaf-3ec0-6eba-0e6cb18971eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686347(v=AX.60)
ms:contentKeyID: 49710049
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustLedgerAccounts Upgrade Script [AX 2012]


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
<td><p>updateCustLedgerAccounts</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates CustInterest field of the CustLedgerAccounts table. Also transforms the old accounts or dimension field to the new account or dimension fields in Microsoft Dynamics AX 2012.</p></td>
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
<td><p>CustLedgerAccounts</p></td>
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
<th><p>From Table: CustLedgerAccounts</p></th>
<th><p>To Table: CustLedgerAccounts</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ClearingAccount</p></td>
<td><p>ClearingLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>LiabilitiesForDiscountAccount</p></td>
<td><p>LiabilitiesForDiscountLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>SumAccount</p></td>
<td><p>SummaryLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>VATprepaymentsAccount</p></td>
<td><p>VATPrepaymentsLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>WriteOffAccount</p></td>
<td><p>WriteOffLedgerDimension</p></td>
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
<td><p>CustLedgerAccounts</p></td>
<td><p>ClearingLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>CustLedgerAccounts</p></td>
<td><p>LiabilitiesForDiscountLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>CustLedgerAccounts</p></td>
<td><p>SummaryLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>CustLedgerAccounts</p></td>
<td><p>VATPrepaymentsLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>CustLedgerAccounts</p></td>
<td><p>WriteOffLedgerDimension</p></td>
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
<td><p>custLedgerAccounts</p></td>
<td><p>DEL_InterestCode</p></td>
</tr>
<tr class="even">
<td><p>CustLedgerAccounts</p></td>
<td><p>ClearingAccount</p></td>
</tr>
<tr class="odd">
<td><p>CustLedgerAccounts</p></td>
<td><p>LiabilitiesForDiscountAccount</p></td>
</tr>
<tr class="even">
<td><p>CustLedgerAccounts</p></td>
<td><p>SumAccount</p></td>
</tr>
<tr class="odd">
<td><p>CustLedgerAccounts</p></td>
<td><p>VATPrepaymentsAccount</p></td>
</tr>
<tr class="even">
<td><p>CustLedgerAccounts</p></td>
<td><p>WriteOffAccount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

