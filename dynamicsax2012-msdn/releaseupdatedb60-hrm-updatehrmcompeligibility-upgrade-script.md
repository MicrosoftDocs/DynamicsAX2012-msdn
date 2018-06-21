---
title: ReleaseUpdateDB60_HRM.updateHRMCompEligibility Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMCompEligibility Upgrade Script
ms:assetid: 5b7c0aa8-eb49-048e-9460-60656dcd50fa
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736309(v=AX.60)
ms:contentKeyID: 49708484
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMCompEligibility Upgrade Script [AX 2012]


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
<td><p>updateHRMCompEligibility</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Unions field in the HRMCompEligibility table with the values that correspond from the RecId field in the HcmUnions table. Updates the JobType field in the HRMCompEligibility table with the value that corresponds from the RecId field in the HcmJobType table. Updates the JobFunction field in the HRMCompEligibility table with the value that corresponds from the RecId field in the HcmJobFunction table. Updates the Department field in the HRMCompEligibility table with the value that corresponds from the Party field in the DirPartyInternalOrganizationTable table, which is a foreign key to the OMDepartment table.</p></td>
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
<td><p>HRMCompEligibility</p></td>
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
<th><p>From Table: HRMCompEligibility</p></th>
<th><p>To Table: HRMCompEligibility</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_JobId</p></td>
<td><p>Job</p></td>
</tr>
<tr class="even">
<td><p>del_JobFunctionId</p></td>
<td><p>JobFunction</p></td>
</tr>
<tr class="odd">
<td><p>del_JobTypeId</p></td>
<td><p>JobType</p></td>
</tr>
<tr class="even">
<td><p>del_UnionId</p></td>
<td><p>Union</p></td>
</tr>
<tr class="odd">
<td><p>del_OrganizationUnitId</p></td>
<td><p>Department</p></td>
</tr>
<tr class="even">
<td><p>del_LocationId</p></td>
<td><p>CompLocation</p></td>
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
<td><p>HRMCompEligibility</p></td>
<td><p>Department</p></td>
<td><p>OMDepartmentRecId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>JobFunction</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>JobType</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Unions</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Job</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>CompLocation</p></td>
<td><p>RefRecId</p></td>
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
<td><p>HRMCompEligibility</p></td>
<td><p>del_JobID</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>del_JobFunctionId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>del_JobTypeId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>del_UnionId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>del_OrganizationUnitId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>del_LocationId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

