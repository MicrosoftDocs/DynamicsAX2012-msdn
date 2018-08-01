---
title: ReleaseUpdateDB60_Basic.updateMappingFields Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateMappingFields Upgrade Script
ms:assetid: e656fe05-4001-ed5f-2a58-38346afcff90
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719799(v=AX.60)
ms:contentKeyID: 49711872
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateMappingFields Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateMappingFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Adds special field mapping for GAB tables.</p></td>
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
<td><p>ReleaseUpdateSpecialFieldMapping</p></td>
</tr>
<tr class="even">
<td><p>DirPartyTable</p></td>
</tr>
<tr class="odd">
<td><p>DirPartyRelationship</p></td>
</tr>
<tr class="even">
<td><p>DirRelationshipTypeTable</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>Shadow_DirPartyTable</p></td>
</tr>
<tr class="odd">
<td><p>HcmContractorAffiliation</p></td>
</tr>
<tr class="even">
<td><p>DirPerson</p></td>
</tr>
<tr class="odd">
<td><p>DirOrganization</p></td>
</tr>
<tr class="even">
<td><p>DirOrganizationBase</p></td>
</tr>
<tr class="odd">
<td><p>OMInternalOrganization</p></td>
</tr>
<tr class="even">
<td><p>Shadow_CompanyInfo</p></td>
</tr>
<tr class="odd">
<td><p>OMOperatingUnit</p></td>
</tr>
<tr class="even">
<td><p>OMDepartment</p></td>
</tr>
<tr class="odd">
<td><p>OMTeam</p></td>
</tr>
<tr class="even">
<td><p>HcmEmployeeAffiliation</p></td>
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
<th><p>From Table: DirPartyTable</p></th>
<th><p>To Table: DirPartyTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaId</p></td>
<td><p>DEL_dataAreaId</p></td>
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
<th><p>From Table: DirPartyRelationship</p></th>
<th><p>To Table: DirPartyRelationship</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaId</p></td>
<td><p>DEL_dataAreaId</p></td>
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
<th><p>From Table: DirRelationshipTypeTable</p></th>
<th><p>To Table: DirRelationshipTypeTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaId</p></td>
<td><p>DEL_dataAreaId</p></td>
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
<th><p>To Table: CompanyInfo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ModifiedBy</p></td>
<td><p>DEL_ModifiedBy</p></td>
</tr>
<tr class="even">
<td><p>ModifiedDateTime</p></td>
<td><p>DEL_ModifiedDateTime</p></td>
</tr>
<tr class="odd">
<td><p>DEL_ModifiedTime</p></td>
<td><p>DEL_ModTime</p></td>
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
<th><p>From Table: Shadow_DirPartyTable</p></th>
<th><p>To Table: DirPartyTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RefRecId</p></td>
<td><p>RecId</p></td>
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
<th><p>From Table: DirPerson</p></th>
<th><p>To Table: DirPerson</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>Shadow_DataAreaId</p></td>
<td><p>DEL_DirPerson_Shadow_DataAreaId</p></td>
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
<th><p>From Table: DirOrganization</p></th>
<th><p>To Table: DirOrganization</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>Shadow_DataAreaId</p></td>
<td><p>DEL_DirOrganization_Shadow_DataAreaId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<th><p>From Table: DirOrganizationBase</p></th>
<th><p>To Table: DirOrganizationBase</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>Shadow_DataAreaId</p></td>
<td><p>DEL_DirOrgBase_Shadow_DataAreaId</p></td>
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
<th><p>From Table: OMInternalOrganization</p></th>
<th><p>To Table: OMInternalOrganization</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>Shadow_DataAreaId</p></td>
<td><p>DEL_Shadow_DataAreaId</p></td>
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
<th><p>From Table: Shadow_CompanyInfo</p></th>
<th><p>To Table: Shadow_CompanyInfo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>RelationType</p></td>
<td><p>RelationType</p></td>
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
<th><p>From Table: OMOperatingUnit</p></th>
<th><p>To Table: OMOperatingUnit</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>Shadow_DataAreaId</p></td>
<td><p>DEL_OMOperatingUnit_Shadow_DataAreaId</p></td>
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
<th><p>From Table: OMDepartment</p></th>
<th><p>To Table: OMDepartment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>Shadow_DataAreaId</p></td>
<td><p>DEL_OMDepartment_Shadow_DataAreaId</p></td>
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
<th><p>From Table: OMTeam</p></th>
<th><p>To Table: OMTeam</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>Shadow_DataAreaId</p></td>
<td><p>DEL_OMTeam_Shadow_DataAreaId</p></td>
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
<th><p>From Table: HcmEmployeeAffiliation</p></th>
<th><p>To Table: HcmEmployeeAffiliation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkerAffiliationRecId</p></td>
<td><p>RecId</p></td>
</tr>
<tr class="even">
<td><p>WorkerAffiliationRecId</p></td>
<td><p>RecId</p></td>
</tr>
</tbody>
</table>

  


