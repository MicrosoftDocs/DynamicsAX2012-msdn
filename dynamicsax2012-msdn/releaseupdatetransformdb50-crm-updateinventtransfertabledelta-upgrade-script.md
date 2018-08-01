---
title: ReleaseUpdateTransformDB50_CRM.updateInventTransferTableDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_CRM.updateInventTransferTableDelta Upgrade Script
ms:assetid: d91a2853-8335-9a1d-e9dd-d3ee28df0884
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737137(v=AX.60)
ms:contentKeyID: 49711580
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_CRM.updateInventTransferTableDelta Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateInventTransferTableDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the delivery postal address in the InventTransferTable table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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
<td><p>InventTransferTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert postal address data to the new logistics postal address model for Microsoft Dynamics AX 2012. The delivery postal address for the InventTransferTable table will be kept as a reference to the LogisticsPostalAddress record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: InventTransferTable</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FromAddressCountyRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>FromAddressState</p></td>
<td><p>State</p></td>
</tr>
<tr class="odd">
<td><p>FromAddressCounty</p></td>
<td><p>County</p></td>
</tr>
<tr class="even">
<td><p>FromAddressZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="odd">
<td><p>FromAddressCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p>FromAddressStreet</p></td>
<td><p>Street</p></td>
</tr>
<tr class="odd">
<td><p>ToAddressCountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>ToAddressState</p></td>
<td><p>State</p></td>
</tr>
<tr class="odd">
<td><p>ToAddressCounty</p></td>
<td><p>County</p></td>
</tr>
<tr class="even">
<td><p>ToAddressZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="odd">
<td><p>ToAddressCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p>ToAddressStreet</p></td>
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
<th><p>To Table: Shadow_InventTransferTable_GAB</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FromPostalAddress</p></td>
</tr>
<tr class="even">
<td><p>Location</p></td>
<td><p>FromLocation</p></td>
</tr>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ToPostalAddress</p></td>
</tr>
<tr class="even">
<td><p>Location</p></td>
<td><p>ToLocation</p></td>
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
<td><p>InventTransferTable</p></td>
<td><p>FromPostalAddress</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
<td><p>FromLocation</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>InventTransferTable</p></td>
<td><p>ToPostalAddress</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
<td><p>ToLocation</p></td>
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
<td><p>InventTransferTable</p></td>
<td><p>FromAddressCountyRegionId</p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
<td><p>FromAddressState</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferTable</p></td>
<td><p>FromAddressCounty</p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
<td><p>FromAddressZipCode</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferTable</p></td>
<td><p>FromAddressCity</p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
<td><p>FromAddressStreet</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferTable</p></td>
<td><p>ToAddressCountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
<td><p>ToAddressState</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferTable</p></td>
<td><p>ToAddressCounty</p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
<td><p>ToAddressZipCode</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferTable</p></td>
<td><p>ToAddressCity</p></td>
</tr>
<tr class="even">
<td><p>InventTransferTable</p></td>
<td><p>ToAddressStreet</p></td>
</tr>
</tbody>
</table>

  


