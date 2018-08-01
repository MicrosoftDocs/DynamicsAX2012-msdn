---
title: ReleaseUpdateDB60_Vend.updateVendPackingSlipVersionCC Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendPackingSlipVersionCC Upgrade Script
ms:assetid: 6c0d7c7a-32ba-8566-ae42-6ba0efbcdc8c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685703(v=AX.60)
ms:contentKeyID: 49708904
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendPackingSlipVersionCC Upgrade Script [AX 2012]


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
<td><p>updateVendPackingSlipVersionCC</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the VendPackingSlipVersion table from the VendPackingSlipJour table. The VersionDateTime field is set to the current UTC time.</p></td>
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
<td><p>VendPackingSlipJour</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipVersion</p></td>
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
<th><p>From Table: VendPackingSlipJour</p></th>
<th><p>To Table: VendPackingSlipVersion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>InternalPackingSlipId</p></td>
<td><p>InternalPackingSlipId</p></td>
</tr>
<tr class="even">
<td><p>LedgerVoucher</p></td>
<td><p>LedgerVoucher</p></td>
</tr>
<tr class="odd">
<td><p>CostLedgerVoucher</p></td>
<td><p>LedgerVoucher</p></td>
</tr>
<tr class="even">
<td><p>InterCompanyLedgerVoucher</p></td>
<td><p>InterCompanyLedgerVoucher</p></td>
</tr>
<tr class="odd">
<td><p>Qty</p></td>
<td><p>Qty</p></td>
</tr>
<tr class="even">
<td><p>Volume</p></td>
<td><p>Volume</p></td>
</tr>
<tr class="odd">
<td><p>Weight</p></td>
<td><p>Weight</p></td>
</tr>
<tr class="even">
<td><p>ParmId</p></td>
<td><p>ParmId</p></td>
</tr>
<tr class="odd">
<td><p>AccountingDate</p></td>
<td><p>DeliveryDate</p></td>
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
<td><p>VendPackingSlipVersion</p></td>
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
<td><p>VendPackingSlipJour</p></td>
<td><p>Qty</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipJour</p></td>
<td><p>Volume</p></td>
</tr>
<tr class="odd">
<td><p>VendPackingSlipJour</p></td>
<td><p>Weight</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipJour</p></td>
<td><p>Printed</p></td>
</tr>
<tr class="odd">
<td><p>VendPackingSlipJour</p></td>
<td><p>LedgerVoucher</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipJour</p></td>
<td><p>ParmId</p></td>
</tr>
<tr class="odd">
<td><p>VendPackingSlipJour</p></td>
<td><p>InternalPackingSlipId</p></td>
</tr>
<tr class="even">
<td><p>VendPackingSlipJour</p></td>
<td><p>InterCompanyLedgerVoucher</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

