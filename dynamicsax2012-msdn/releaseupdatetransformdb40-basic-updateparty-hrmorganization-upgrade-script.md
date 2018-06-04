---
title: ReleaseUpdateTransformDB40_Basic.updateParty_HRMOrganization Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Basic.updateParty_HRMOrganization Upgrade Script
ms:assetid: 3f84025b-26e2-cb6c-1b74-c26179813b3c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718790(v=AX.60)
ms:contentKeyID: 49707836
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Basic.updateParty\_HRMOrganization Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateParty_HRMOrganization</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transform data in the HRMOrganization table into the DirPartyTable table and the new logistics address model for Microsoft Dynamics AX 2012.</p></td>
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
<td><p>HRMOrganization</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to update the HRMOrganization table. The party will be kept as a reference to the DirPartyTable record. The addresses that are associated to the party will be upgraded into the new logistics address model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMOrganization</p></th>
<th><p>To Table: DirPartyTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>LanguageId</p></td>
<td><p>LanguageId</p></td>
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
<th><p>From Table: HRMOrganization</p></th>
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
<td><p>ZipCodeId</p></td>
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
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMOrganization</p></th>
<th><p>To Table: LogisticsElectronicAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Phone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>PhoneLocal</p></td>
<td><p>LocatorExtension</p></td>
</tr>
<tr class="odd">
<td><p>TeleFax</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>Telex</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>URL</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>CellularPhone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>Email</p></td>
<td><p>Locator</p></td>
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
<td><p>HRMOrganization</p></td>
<td><p>Party</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirPartyTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>DirOrganization</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirOrganizationName</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>DirPerson</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirPersonName</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>DirOrganizationBase</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

