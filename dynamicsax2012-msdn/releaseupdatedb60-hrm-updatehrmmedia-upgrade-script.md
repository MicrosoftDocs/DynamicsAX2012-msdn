---
title: ReleaseUpdateDB60_HRM.updateHRMMedia Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMMedia Upgrade Script
ms:assetid: a248219e-3b04-d348-a55d-beecbb05c9f2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736745(v=AX.60)
ms:contentKeyID: 49710177
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMMedia Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHRMMedia</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Location field of the HRMMedia table.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>LogisticsAddressZipCode</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddresssCity</p></td>
</tr>
<tr class="odd">
<td><p>HRMMedia</p></td>
</tr>
<tr class="even">
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsPostalAddress</p></td>
</tr>
</tbody>
</table>


## Remarks

Creates a new record in the LogisticsLocation table and the LogisticsPostalAddress table based on address information in the HRMMeida table. Updates the Location field of the HRMMeida table with the corresponding value of the RecId field of the LogisticsLocation table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMMedia</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>StateId</p></td>
<td><p>State</p></td>
</tr>
<tr class="odd">
<td><p>CountyId</p></td>
<td><p>County</p></td>
</tr>
<tr class="even">
<td><p>City</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>ZipCodeId</p></td>
<td><p>ZipCode</p></td>
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


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMMedia</p></th>
<th><p>To Table: LogisticsLocation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HrmMediaId</p></td>
<td><p>Description</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name:</p></th>
<th><p>New Table Name:</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>CountryRegionId</p></td>
<td><p>DEL_CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>StateId</p></td>
<td><p>DEL_StateId</p></td>
</tr>
<tr class="even">
<td><p>CountyId</p></td>
<td><p>DEL_CountyId</p></td>
</tr>
<tr class="odd">
<td><p>City</p></td>
<td><p>DEL_City</p></td>
</tr>
<tr class="even">
<td><p>ZipCodeId</p></td>
<td><p>DEL_ZipCodeId</p></td>
</tr>
<tr class="odd">
<td><p>Street</p></td>
<td><p>DEL_Street</p></td>
</tr>
<tr class="even">
<td><p>Address</p></td>
<td><p>DEL_Address</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

