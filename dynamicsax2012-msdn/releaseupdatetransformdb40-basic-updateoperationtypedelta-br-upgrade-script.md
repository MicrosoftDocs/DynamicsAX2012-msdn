---
title: ReleaseUpdateTransformDB40_Basic.updateOperationTypeDelta_BR Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Basic.updateOperationTypeDelta_BR Upgrade Script
ms:assetid: ea40a1ad-8ecd-6ded-85f3-649681ab9cf6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719858(v=AX.60)
ms:contentKeyID: 49711930
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Basic.updateOperationTypeDelta\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateOperationTypeDelta_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script is used for updating the sales and purchase operation types.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p>
<p>Pre-processing60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>Basic</p></td>
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
<td><p>SalesPurchOperationType_BR</p></td>
</tr>
<tr class="even">
<td><p>Shadow_CFOPMatrix_BR</p></td>
</tr>
<tr class="odd">
<td><p>TmpOperationTypesToResolve</p></td>
</tr>
</tbody>
</table>


## Remarks

The script creates new \<c\>SalesPurchOperationType\_BR\</c\> records and the \<c\>Shadow\_CFOPMatrix\_BR\</c\> records to upgrade sales and purchase operation types.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TmpOperationTypesToResolve</p></th>
<th><p>To Table: SalesPurchOperationType</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OperationId</p></td>
<td><p>OperationTypeId</p></td>
</tr>
<tr class="even">
<td><p>Name</p></td>
<td><p>Name</p></td>
</tr>
<tr class="odd">
<td><p>CustPostingProfile</p></td>
<td><p>CustPostingProfile</p></td>
</tr>
<tr class="even">
<td><p>VendPostingProfile</p></td>
<td><p>VendPostingProfile</p></td>
</tr>
<tr class="odd">
<td><p>InventControl</p></td>
<td><p>CreateInventTrans</p></td>
</tr>
<tr class="even">
<td><p>DlvTransitDeposit</p></td>
<td><p>InventLocationIdTransit</p></td>
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
<td><p>SalesPurchOperationType_BR</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>SalesOperationType_BR</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PurchOperationType_BR</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


