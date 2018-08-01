---
title: ReleaseUpdateTransformDB40_CRM.updateSalesQuotationTable Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_CRM.updateSalesQuotationTable Upgrade Script
ms:assetid: f7d7bdae-96eb-9cca-2a6a-b0bcd7d975f4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737618(v=AX.60)
ms:contentKeyID: 49712311
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_CRM.updateSalesQuotationTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_CRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateSalesQuotationTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the delivery postal address in the SalesQuotationTable table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
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
<td><p>SalesQuotationTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert postal address data to the new logistics postal address model for Microsoft Dynamics AX 2012. The delivery postal address for the SalesQuotationTable table will be kept as a reference to the LogisticsPostalAddress record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: SalesQuotationTable</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DeliveryAddress</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>DeliveryCountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryState</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>DeliveryCounty</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
<td><p>DeliveryCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>DeliveryStreet</p></td>
<td><p>Street</p></td>
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
<th><p>From Table: LogisticsPostalAddress</p></th>
<th><p>To Table: Shadow_SalesQuotationTable_GAB</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DeliveryPostalAdress</p></td>
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
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryPostalAdress</p></td>
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
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryAddress</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryCountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryState</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryCounty</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryZipCode</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryCity</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationTable</p></td>
<td><p>DeliveryStreet</p></td>
</tr>
</tbody>
</table>

  


