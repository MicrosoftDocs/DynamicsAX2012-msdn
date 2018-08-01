---
title: ReleaseUpdateDB60_HRM.updateHRMCompEventLineComposite Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMCompEventLineComposite Upgrade Script
ms:assetid: 7478da4b-3122-c41e-13a3-8631c880dd39
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719261(v=AX.60)
ms:contentKeyID: 49709054
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMCompEventLineComposite Upgrade Script [AX 2012]


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
<td><p>updateHRMCompEventLineComposite</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CompensationLevel field in the HRMCompEventLineComposite table with the corresponding value from the record ID field in the HcmCompensationLevel table. Updates the Department field in the HRMCompEventLineComposite table with the corresponding value from the Party field in the DirPartyInternalOrganizationTable table, which is a foreign key to the OMDepartment table.</p></td>
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
<td><p>HRMCompEventLineComposite</p></td>
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
<th><p>From Table: HRMCompEventLineComposite</p></th>
<th><p>To Table: HRMCompEventLineComposite</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_OrganizationUnitId</p></td>
<td><p>Department</p></td>
</tr>
<tr class="even">
<td><p>del_EmplId</p></td>
<td><p>Worker</p></td>
</tr>
<tr class="odd">
<td><p>del_PositionId</p></td>
<td><p>Position</p></td>
</tr>
<tr class="even">
<td><p>del_LevelId</p></td>
<td><p>CompensationLevel</p></td>
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
<td><p>HRMCompEventLineComposite</p></td>
<td><p>Department</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Worker</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Position</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>CompensationLevel</p></td>
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
<td><p>HRMCompEventLineComposite</p></td>
<td><p>del_OrganizationUnitId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>del_EmplId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>del_PositionId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>del_LevelId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

