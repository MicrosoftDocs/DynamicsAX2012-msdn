---
title: ReleaseUpdateTransformDB50_GAB.updateIntrastatParameters Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_GAB.updateIntrastatParameters Upgrade Script
ms:assetid: 3442492b-b4ee-f0c0-b114-2a40fe1f32a1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685122(v=AX.60)
ms:contentKeyID: 49707575
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_GAB.updateIntrastatParameters Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_GAB</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateIntrastatParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the postal address in the IntrastatParameters table.</p></td>
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
<td><p>IntrastatParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to convert postal address data to the new logistics postal address model for Microsoft Dynamics AX 2012. The location in the IntrastatParameters will be kept as a reference to the LogisticsLocation record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: IntrastatParameters</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AgentAddress</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>AgentCountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>AgentState</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>AgentCounty</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>AgentZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
<td><p>AgentCity</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>AgentStreet</p></td>
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
<th><p>To Table: Shadow_IntrastatParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Location</p></td>
<td><p>AgentLocation</p></td>
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
<td><p>IntrastatParameters</p></td>
<td><p>AgentLocation</p></td>
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
<td><p>IntrastatParameters</p></td>
<td><p>AgentAddress</p></td>
</tr>
<tr class="even">
<td><p>IntrastatParameters</p></td>
<td><p>AgentCountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>IntrastatParameters</p></td>
<td><p>AgentState</p></td>
</tr>
<tr class="even">
<td><p>IntrastatParameters</p></td>
<td><p>AgentCounty</p></td>
</tr>
<tr class="odd">
<td><p>IntrastatParameters</p></td>
<td><p>AgentZipCode</p></td>
</tr>
<tr class="even">
<td><p>IntrastatParameters</p></td>
<td><p>AgentCity</p></td>
</tr>
<tr class="odd">
<td><p>IntrastatParameters</p></td>
<td><p>AgentStreet</p></td>
</tr>
</tbody>
</table>

  


