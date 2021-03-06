﻿---
title: ReleaseUpdateTransformDB50_CRM.updateCzVendAdvanceInvoiceTableDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_CRM.updateCzVendAdvanceInvoiceTableDelta Upgrade Script
ms:assetid: bbbe450e-7d73-68b1-4e93-2de111af87f2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686629(v=AX.60)
ms:contentKeyID: 49710837
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_CRM.updateCzVendAdvanceInvoiceTableDelta Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_CRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCzVendAdvanceInvoiceTableDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the address fields to the &lt;c&gt;PostalAddress&lt;/c&gt; field in the &lt;c&gt;CzVendAdvanceInvoiceTable&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>CzVendAdvanceInvoiceTable</p></td>
</tr>
<tr class="even">
<td><p>Shadow_CzVendAdvanceInvoiceTable_GAB</p></td>
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
<th><p>From Table: CzVendAdvanceInvoiceTable</p></th>
<th><p>To Table: Shadow_CzVendAdvanceInvoiceTable_GAB</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Address</p></td>
<td><p>PostalAddress</p></td>
</tr>
<tr class="even">
<td><p>City</p></td>
<td><p>PostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>CountryRegionId</p></td>
<td><p>PostalAddress</p></td>
</tr>
<tr class="even">
<td><p>County</p></td>
<td><p>PostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>State</p></td>
<td><p>PostalAddress</p></td>
</tr>
<tr class="even">
<td><p>Street</p></td>
<td><p>PostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>Zipcode</p></td>
<td><p>PostalAddress</p></td>
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
<td><p>CzVendAdvanceInvoiceTable</p></td>
<td><p>PostalAddress</p></td>
<td><p>LogisticsPostalAddressRecId</p></td>
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
<td><p>CzVendAdvanceInvoiceTable</p></td>
<td><p>DEL_Address</p></td>
</tr>
<tr class="even">
<td><p>CzVendAdvanceInvoiceTable</p></td>
<td><p>DEL_City</p></td>
</tr>
<tr class="odd">
<td><p>CzVendAdvanceInvoiceTable</p></td>
<td><p>DEL_CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>CzVendAdvanceInvoiceTable</p></td>
<td><p>DEL_County</p></td>
</tr>
<tr class="odd">
<td><p>CzVendAdvanceInvoiceTable</p></td>
<td><p>DEL_State</p></td>
</tr>
<tr class="even">
<td><p>CzVendAdvanceInvoiceTable</p></td>
<td><p>DEL_Street</p></td>
</tr>
<tr class="odd">
<td><p>CzVendAdvanceInvoiceTable</p></td>
<td><p>DEL_ZipCode</p></td>
</tr>
</tbody>
</table>

  


