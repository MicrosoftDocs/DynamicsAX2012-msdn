---
title: ReleaseUpdateDB60_Vend.updateVendPaymModeTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendPaymModeTable Upgrade Script
ms:assetid: 65d97194-556a-0dc2-9fc9-c3dbbb34eb68
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719210(v=AX.60)
ms:contentKeyID: 49708749
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendPaymModeTable Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateVendPaymModeTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The DimUse needs to be converted to the dimensionAttributeSet as per the new accounts and dimension model. Also transforms data from the InterCoAccount field to the InterCompanyLedgerDimension field and from the PaymAccount field to the PaymentLedgerDimension field.</p></td>
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
<td><p>VendPaymModeTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert the account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendPaymModeTable</p></th>
<th><p>To Table: VendPaymModeTable</p></th>
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
<td><p>VendPaymModeTable</p></td>
<td><p>DimensionAttributeSet</p></td>
<td><p>DimensionEnumeration</p></td>
</tr>
<tr class="even">
<td><p>VendPaymModeTable</p></td>
<td><p>InterCompanyLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>VendPaymModeTable</p></td>
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
<td><p>VendPaymModeTable</p></td>
<td><p>DimUse</p></td>
</tr>
<tr class="even">
<td><p>VendPaymModeTable</p></td>
<td><p>InterAccount</p></td>
</tr>
<tr class="odd">
<td><p>VendPaymModeTable</p></td>
<td><p>PaymAccount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

