---
title: ReleaseUpdateDB60_HRM.updateHrmEmployeeContactLogistics Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHrmEmployeeContactLogistics Upgrade Script
ms:assetid: 5eee20c0-3b31-aa8b-bdc8-a9550568e92c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719018(v=AX.60)
ms:contentKeyID: 49708558
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHrmEmployeeContactLogistics Upgrade Script 


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
<td><p>updateHrmEmployeeContactLogistics</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Performs an upgrade of the address-related information for worker contacts to the GAB.</p></td>
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
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="even">
<td><p>LogisticsPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsAddressCounty</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddresssCity</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsAddressState</p></td>
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
<td><p>LogisticsElectronicAddress</p></td>
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
<th><p>From Table: HrmEmployeeContact</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_countryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>DEL_countyId</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>zipCodeId</p></td>
<td><p>ZipCodeRecId</p></td>
</tr>
<tr class="even">
<td><p>DEL_stateId</p></td>
<td><p>State</p></td>
</tr>
<tr class="odd">
<td><p>DEL_city</p></td>
<td><p>CityRecId</p></td>
</tr>
<tr class="even">
<td><p>DEL_street</p></td>
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
<th><p>From Table: HrmEmployeeContact</p></th>
<th><p>To Table: LogisticsElectronicAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>phone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>phoneLocal</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>telex</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>Email</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>teleFax</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>phoneMobile</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>Sms</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>Pager</p></td>
<td><p>Locator</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

