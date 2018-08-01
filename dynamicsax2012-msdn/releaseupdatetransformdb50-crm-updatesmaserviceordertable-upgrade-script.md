---
title: ReleaseUpdateTransformDB50_CRM.updateSMAServiceOrderTable Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_CRM.updateSMAServiceOrderTable Upgrade Script
ms:assetid: c8bbe1ab-7592-bfd5-7160-cf475d7ad8d9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719596(v=AX.60)
ms:contentKeyID: 49711163
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_CRM.updateSMAServiceOrderTable Upgrade Script 


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
<td><p>updateSMAServiceOrderTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the delivery postal address in the SMAServiceOrderTable table.</p></td>
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
<td><p>SMAServiceOrderTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert postal address data to the new logistics postal address model for Microsoft Dynamics AX 2012. The delivery postal address for the SMAServiceOrderTable table will be kept as a reference to the LogisticsPostalAddress record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: SMAServiceOrderTable</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ServiceAddress</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>ServiceAddressCountryRegion</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>ServiceAddressState</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>ServiceAddressCounty</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>ServiceAddressZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
<td><p>ServiceAddressCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>ServiceAddressStreet</p></td>
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
<th><p>To Table: Shadow_SMAServiceOrderTable_GAB</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Location</p></td>
<td><p>ServiceLocation</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>ServicePostalAddress</p></td>
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
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServiceLocation</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServicePostalAddress</p></td>
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
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServiceAddress</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServiceAddressCountryRegion</p></td>
</tr>
<tr class="odd">
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServiceAddressState</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServiceAddressCounty</p></td>
</tr>
<tr class="odd">
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServiceAddressZipCode</p></td>
</tr>
<tr class="even">
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServiceAddressCity</p></td>
</tr>
<tr class="odd">
<td><p>SMAServiceOrderTable</p></td>
<td><p>ServiceAddressStreet</p></td>
</tr>
</tbody>
</table>

  


