---
title: ReleaseUpdateDB60_Cust.updateCustPaymModeTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustPaymModeTable Upgrade Script
ms:assetid: 0f8bd959-8bcb-2611-e783-ccc23d0356a5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735763(v=AX.60)
ms:contentKeyID: 49706663
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustPaymModeTable Upgrade Script 


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
<td><p>updateCustPaymModeTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts the dimension DimUse enumeration type to the DimensionAttributeSet field as per the new accounts and dimensions model. Also transforms data from the InterCoAccount and PayAccount fields to the InterCompanyLedgerDimension and PaymentLedgerDimension fields, respectively.</p></td>
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
<td><p>CustPaymModeTable</p></td>
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
<th><p>From Table: CustPaymModeTable</p></th>
<th><p>To Table: CustPaymModeTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>InterCoAccount</p></td>
<td><p>InterCompanyLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>PaymAccount</p></td>
<td><p>PaymentLedgerDimension</p></td>
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
<td><p>CustPaymModeTable</p></td>
<td><p>DimensionAttributeSet</p></td>
<td><p>DimensionEnumeration</p></td>
</tr>
<tr class="even">
<td><p>CustPaymModeTable</p></td>
<td><p>InterCompanyLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>CustPaymModeTable</p></td>
<td><p>PaymentLedgerDimension</p></td>
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
<td><p>CustPaymModeTable</p></td>
<td><p>DimUse</p></td>
</tr>
<tr class="even">
<td><p>CustPaymModeTable</p></td>
<td><p>InterCoAccount</p></td>
</tr>
<tr class="odd">
<td><p>CustPaymModeTable</p></td>
<td><p>PaymAccount</p></td>
</tr>
</tbody>
</table>

  


