---
title: ReleaseUpdateDB60_HRM.updatehrmEmployeeContact Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updatehrmEmployeeContact Upgrade Script
ms:assetid: afc632d2-4d88-c4ca-ddf4-f315e16310fb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686589(v=AX.60)
ms:contentKeyID: 49710544
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updatehrmEmployeeContact Upgrade Script [AX 2012]


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
<td><p>updatehrmEmployeeContact</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Moves the data for worker contacts into the GAB.</p></td>
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
<tr class="even">
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
<td><p>HrmEmployeeContact</p></td>
</tr>
<tr class="even">
<td><p>HcmPersonPrivateDetails</p></td>
</tr>
<tr class="odd">
<td><p>HcmEmergencyContactRelationship</p></td>
</tr>
<tr class="even">
<td><p>DirPartyTable</p></td>
</tr>
<tr class="odd">
<td><p>DirPerson</p></td>
</tr>
<tr class="even">
<td><p>DirPersonName</p></td>
</tr>
<tr class="odd">
<td><p>DirNameAffix</p></td>
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
<th><p>To Table: DirPartyRelationship</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>StartDate</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="even">
<td><p>EndDate</p></td>
<td><p>ValidTo</p></td>
</tr>
<tr class="odd">
<td><p>emplId</p></td>
<td><p>ParentParty</p></td>
</tr>
<tr class="even">
<td><p>emplId</p></td>
<td><p>ChildParty</p></td>
</tr>
<tr class="odd">
<td><p>Relatives</p></td>
<td><p>RelationshipTypeID</p></td>
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
<th><p>To Table: DirNameAffix</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Salutation</p></td>
<td><p>Affix</p></td>
</tr>
<tr class="even">
<td><p>GenerationalSuffix</p></td>
<td><p>Affix</p></td>
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
<th><p>To Table: DirPersonName</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FirstName</p></td>
<td><p>FirstName</p></td>
</tr>
<tr class="even">
<td><p>MiddleName</p></td>
<td><p>MiddleName</p></td>
</tr>
<tr class="odd">
<td><p>LastName</p></td>
<td><p>LastName</p></td>
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
<th><p>To Table: DirPartyTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nickname</p></td>
<td><p>KnownAs</p></td>
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
<th><p>To Table: DirPerson</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initial</p></td>
<td><p>Initials</p></td>
</tr>
<tr class="even">
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
<th><p>From Table: HrmEmployeeContact</p></th>
<th><p>To Table: HcmPersonPrivateDetails</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BirthDate</p></td>
<td><p>BirthDate</p></td>
</tr>
<tr class="even">
<td><p>DeceasedDate</p></td>
<td><p>DeceasedDate</p></td>
</tr>
<tr class="odd">
<td><p>Citizenship</p></td>
<td><p>CitizenshipCountryRegion</p></td>
</tr>
<tr class="even">
<td><p>Gender</p></td>
<td><p>Gender</p></td>
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
<th><p>From Table: HcmEmployeeContact</p></th>
<th><p>To Table: HcmEmergencyContactRelationship</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PrimarySecondary</p></td>
<td><p>IsPrimary</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

