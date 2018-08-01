---
title: ReleaseUpdateDB60_HRM.updateOMTeam Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateOMTeam Upgrade Script
ms:assetid: 0f6cd409-e6a4-4345-9e30-39d539b594bc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735762(v=AX.60)
ms:contentKeyID: 49706662
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateOMTeam Upgrade Script 


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
<td><p>updateOMTeam</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the TeamMembershipCriterion and description fields in the OMTeam table.</p></td>
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
<td><p>OMTeamMembershipCriterion</p></td>
</tr>
<tr class="even">
<td><p>OMTeam</p></td>
</tr>
</tbody>
</table>


## Remarks

Creates two team types in the OMTeamMembershipCriterion table and associates them with the TeamMembershipCriterion field in the OMTeam table. Populates the description field in the OMTeam table by using the description field in the DEL\_DirPartyInternalOrganizationTable table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_DirPartyInternalOrganizationTable</p></th>
<th><p>To Table: OMTeam</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>description</p></td>
<td><p>description</p></td>
</tr>
<tr class="even">
<td><p>UnitType</p></td>
<td><p>TeamMembershipCriterion</p></td>
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
<td><p>OMTeam</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>OMTeamMembershipCriterion</p></td>
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
<td><p>DEL_DirPartyInternalOrganizationTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


