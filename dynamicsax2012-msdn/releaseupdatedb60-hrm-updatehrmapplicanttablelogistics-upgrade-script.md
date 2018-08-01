---
title: ReleaseUpdateDB60_HRM.updateHRMApplicantTableLogistics Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMApplicantTableLogistics Upgrade Script
ms:assetid: e71a6875-8668-aa0f-1297-8e0167baa8cb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719795(v=AX.60)
ms:contentKeyID: 49711868
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMApplicantTableLogistics Upgrade Script 


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
<td><p>updateHRMApplicantTableLogistics</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records in the LogisticsLocation table, the LogisticsPostalAddress table, the LogisticsElectronicAddress table, the DirPartyLocation table, and the DirPartyLocationRole table from the HRMApplicantTable table.</p></td>
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
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="even">
<td><p>LogisticsPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsElectronicAddress</p></td>
</tr>
<tr class="even">
<td><p>DEL_AddressCountryRegionUpgrade</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsAddressCounty</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddressState</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsAddresssCity</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddressZipCode</p></td>
</tr>
<tr class="odd">
<td><p>DirPartyLocation</p></td>
</tr>
<tr class="even">
<td><p>DirPartyLocationRole</p></td>
</tr>
<tr class="odd">
<td><p>HRMApplicantTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the Person field of the HRMApplicantTable table with the RecId value of the created DirPerson record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMApplicantTable</p></th>
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
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMApplicantTable</p></th>
<th><p>To Table: LogisticsElectronicAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Phone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>Telefax</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>Email</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>Url</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>Telex</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>CellularPhone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>Sms</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>Pager</p></td>
<td><p>Locator</p></td>
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
<td><p>HRMApplicantTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


