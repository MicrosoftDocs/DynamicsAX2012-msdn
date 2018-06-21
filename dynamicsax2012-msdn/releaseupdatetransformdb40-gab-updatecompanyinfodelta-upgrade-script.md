---
title: ReleaseUpdateTransformDB40_GAB.updateCompanyInfoDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_GAB.updateCompanyInfoDelta Upgrade Script
ms:assetid: 4e6a832b-f819-e3eb-6210-57ed18f44d10
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685465(v=AX.60)
ms:contentKeyID: 49708169
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_GAB.updateCompanyInfoDelta Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_GAB</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCompanyInfoDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates data in the CompanyInfo table.</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>DirPartyTable</p></td>
</tr>
<tr class="odd">
<td><p>DirOrganizationBase</p></td>
</tr>
<tr class="even">
<td><p>DirOrganizationName</p></td>
</tr>
<tr class="odd">
<td><p>OMInternalOrganization</p></td>
</tr>
<tr class="even">
<td><p>CompanyDefaultLocation</p></td>
</tr>
<tr class="odd">
<td><p>DirPartyLocation</p></td>
</tr>
<tr class="even">
<td><p>LogisticsElectronicAddress</p></td>
</tr>
<tr class="odd">
<td><p>DirPartyLocation</p></td>
</tr>
<tr class="even">
<td><p>DirPartyLocationRole</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to convert postal address data to the new logistics postal address model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CompanyInfo</p></th>
<th><p>To Table: DirPartyTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>Name</p></td>
<td><p>NameAlias</p></td>
</tr>
<tr class="odd">
<td><p>LanguageId</p></td>
<td><p>LanguageId</p></td>
</tr>
<tr class="even">
<td><p>DataAreaId</p></td>
<td><p>DEL_DataAreaId</p></td>
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
<th><p>From Table: CompanyInfo</p></th>
<th><p>To Table: DirOrganizationBase</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>Shadow_DataAreaId</p></td>
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
<th><p>From Table: CompanyInfo</p></th>
<th><p>To Table: DirOrganizationName</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Name</p></td>
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
<th><p>From Table: CompanyInfo</p></th>
<th><p>To Table: OmInternalOrganization</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>Shadow_DataAreaId</p></td>
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
<th><p>From Table: CompanyInfo</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Address</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>CountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>State</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>County</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>ZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
<td><p>City</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>Street</p></td>
<td><p>Street</p></td>
</tr>
<tr class="even">
<td><p>CountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>State</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>County</p></td>
<td><p>County</p></td>
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
<th><p>From Table: CompanyInfo</p></th>
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
<tr class="even">
<td><p>Pager</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>SMS</p></td>
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
<td><p>CompanyInfo</p></td>
<td><p>LogisticsLocationRecId</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>DirPartyLocationRecId</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>DirPartyTableRecId</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirPartyTable</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>DirOrganizationBase</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirOrganizationName</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>OMInternalOrganization</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>LogisticsElectronicAddress</p></td>
<td><p></p></td>
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
<td><p>CompanyInfo</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>Address</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>Phone</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>TeleFax</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>CurrencyCode</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>Telex</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>URL</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>Email</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>CellularPhone</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>PhoneLocal</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>EuroCurrencyCode</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>SecondaryCurrencyCode</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>LanguageId</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>Street</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>City</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>Pager</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>SMS</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>CompanyIdNAF</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>PaymInstructionId1</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>PaymInstructionId2</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>PaymInstructionId3</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>PaymInstructionId4</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

