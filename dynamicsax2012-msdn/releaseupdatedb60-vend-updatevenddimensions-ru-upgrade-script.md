---
title: ReleaseUpdateDB60_Vend.updateVendDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendDimensions_RU Upgrade Script
ms:assetid: ff842b70-88dd-9809-c3f1-9e7048e5106a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720181(v=AX.60)
ms:contentKeyID: 49712486
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendDimensions\_RU Upgrade Script 


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
<td><p>updateVendDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from account fields to LedgerDimension fields in the VendParameters and PurchBookVATProcessParameters_RU tables.</p></td>
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
<td><p>VendParameters</p></td>
</tr>
<tr class="even">
<td><p>PurchBookVATProcessParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendParameters</p></th>
<th><p>To Table: VendParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTax25UnrealisedRevenueAcct</p></td>
<td><p>RTax25UnrealisedRevenueLedgerDimension</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchBookVATProcessParameters</p></th>
<th><p>To Table: PurchBookVATProcessParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LedgerAccount</p></td>
<td><p>LedgerDimension</p></td>
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
<td><p>VendParameters</p></td>
<td><p>RTax25UnrealisedRevenueLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>PurchBookVATProcessParameters</p></td>
<td><p>LedgerDimension</p></td>
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
<td><p>VendParameters</p></td>
<td><p>RTax25UnrealisedRevenueAcct</p></td>
</tr>
<tr class="even">
<td><p>PurchBookVATProcessParameters</p></td>
<td><p>LedgerAccount</p></td>
</tr>
</tbody>
</table>

  


