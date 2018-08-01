﻿---
title: ReleaseUpdateTransformDB40_CRM.updateInventTransferJourDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_CRM.updateInventTransferJourDelta Upgrade Script
ms:assetid: 5140baba-31fb-430e-fb45-3547b49c74da
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685522(v=AX.60)
ms:contentKeyID: 49708226
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_CRM.updateInventTransferJourDelta Upgrade Script [AX 2012]


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
<td><p>updateInventTransferJourDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the delivery postal address in the InventTransferJour table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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
<td><p>InventTransferJour</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert postal address data to the new logistics postal address model for Microsoft Dynamics AX 2012. The delivery postal address for the InventTransferJour record will be kept as a reference to the LogisticsPostalAddress record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: InventTransferJour</p></th>
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
<th><p>To Table: Shadow_InventTransferJour_GAB</p></th>
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
<td><p>InventTransferJour</p></td>
<td><p>FromPostalAddress</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>InventTransferJour</p></td>
<td><p>FromLocation</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>InventTransferJour</p></td>
<td><p>ToPostalAddress</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>InventTransferJour</p></td>
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
<td><p>InventTransferJour</p></td>
<td><p>FromAddressCountyRegionId</p></td>
</tr>
<tr class="even">
<td><p>InventTransferJour</p></td>
<td><p>FromAddressState</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferJour</p></td>
<td><p>FromAddressCounty</p></td>
</tr>
<tr class="even">
<td><p>InventTransferJour</p></td>
<td><p>FromAddressZipCode</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferJour</p></td>
<td><p>FromAddressCity</p></td>
</tr>
<tr class="even">
<td><p>InventTransferJour</p></td>
<td><p>FromAddressStreet</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferJour</p></td>
<td><p>ToAddressCountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>InventTransferJour</p></td>
<td><p>ToAddressState</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferJour</p></td>
<td><p>ToAddressCounty</p></td>
</tr>
<tr class="even">
<td><p>InventTransferJour</p></td>
<td><p>ToAddressZipCode</p></td>
</tr>
<tr class="odd">
<td><p>InventTransferJour</p></td>
<td><p>ToAddressCity</p></td>
</tr>
<tr class="even">
<td><p>InventTransferJour</p></td>
<td><p>ToAddressStreet</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

