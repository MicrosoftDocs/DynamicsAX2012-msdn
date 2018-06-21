---
title: ReleaseUpdateTransformDB50_Basic.updateAddressCountryRegionPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.updateAddressCountryRegionPreProcessing Upgrade Script
ms:assetid: 0b774900-3c1d-e64e-9155-bb8cb71c4eac
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735649(v=AX.60)
ms:contentKeyID: 49706560
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.updateAddressCountryRegionPreProcessing Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateAddressCountryRegionPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data in the AddressCountryRegion table to the IntrastatCountryRegionParameters, TaxCountryRegionParameters, LogisticsCountryRegionPaymentIdType_NO, and LogisticsAddressCountryRegion tables.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>CRM</p></td>
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
<td><p>AddressCountryRegion</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to transform the data in the AddressCountryRegion table into the new global address book model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AddressCountryRegion</p></th>
<th><p>To Table: IntrastatCountryRegionParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>IntrastateCode</p></td>
<td><p>IntrastateCode</p></td>
</tr>
<tr class="odd">
<td><p>Type</p></td>
<td><p>CountryRegionType</p></td>
</tr>
<tr class="even">
<td><p>CurrrencyCode</p></td>
<td><p>CurrencyCode</p></td>
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
<th><p>From Table: AddressCountryRegion</p></th>
<th><p>To Table: TaxCountryRegionParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>TaxCode</p></td>
<td><p>SalesTaxCode</p></td>
</tr>
<tr class="odd">
<td><p>TaxVatNumFormatCheck</p></td>
<td><p>CheckTaxExemptNumber</p></td>
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
<th><p>From Table: AddressCountryRegion</p></th>
<th><p>To Table: LogisticsCountryRegionPaymentIdType_NO</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>PaymIdType</p></td>
<td><p>BankCustPaymIdTable</p></td>
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
<th><p>From Table: AddressCountryRegion</p></th>
<th><p>To Table: LogisticsAddressCountryRegion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AddressUseZipPlus4</p></td>
<td><p>AddressUseZipPlus4</p></td>
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
<td><p>IntrastatCountryRegionParameters</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>TaxCountryRegionParameters</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>LogisticsCountryRegionParmentIdType_NO</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddressCountryRegion</p></td>
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
<td><p>AddressCountryRegion</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

