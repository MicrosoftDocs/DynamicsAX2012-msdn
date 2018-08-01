---
title: ReleaseUpdateTransformDB50_GAB.intrastatServicePoint_FI Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_GAB.intrastatServicePoint_FI Upgrade Script
ms:assetid: 8a2152b2-3b99-0580-6bf4-c8acd9c31965
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736394(v=AX.60)
ms:contentKeyID: 49709584
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_GAB.intrastatServicePoint\_FI Upgrade Script 


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
<td><p>intrastatServicePoint_FI</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates new address in the LogisticsLocation table with the address information from the IntrastatServicePoint_FI table and updates the IntrastatServicePoint_FI and Location tables with the LogisticsLocation record ID.</p></td>
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
<td><p>Service</p></td>
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
<td><p>IntrastatServicePoint_FI</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to convert address data to the new global address book model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: IntrastatServicePoint_FI</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Country</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>State</p></td>
<td><p>State</p></td>
</tr>
<tr class="odd">
<td><p>County</p></td>
<td><p>County</p></td>
</tr>
<tr class="even">
<td><p>ZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="odd">
<td><p>City</p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p>Street</p></td>
<td><p>Street</p></td>
</tr>
<tr class="odd">
<td><p>Address</p></td>
<td><p>Address</p></td>
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
<td><p>IntrastatServicePoint_FI</p></td>
<td><p>Location</p></td>
<td><p>LogisticsLocationRoleRecId</p></td>
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
<td><p>IntrastatServicePoint_FI</p></td>
<td><p>Country</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>State</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Address</p></td>
</tr>
</tbody>
</table>

  


