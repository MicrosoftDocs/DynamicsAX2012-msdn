---
title: ReleaseUpdateDB60_HRM.updateHcmEmploymentLeave Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmEmploymentLeave Upgrade Script
ms:assetid: fb91f0c2-82c1-46d3-de47-882b84555bbb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720087(v=AX.60)
ms:contentKeyID: 49712393
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmEmploymentLeave Upgrade Script 


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
<td><p>updateHcmEmploymentLeave</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmEmploymentLeave table from the DEL_HRMEmplLeave table.</p></td>
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
<td><p>HcmEmploymentLeave</p></td>
</tr>
</tbody>
</table>


## Remarks

The Employment field in the HcmEmploymentLeave table is the foreign key to the HcmEmployment table. The LeaveType field in the HcmEmploymentLeave table is the foreign key to the HcmLeaveType table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRMEmplLeave</p></th>
<th><p>To Table: HcmEmploymentLeave</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>StartDate</p></td>
<td><p>StartDate</p></td>
</tr>
<tr class="even">
<td><p>EndDate</p></td>
<td><p>EndDate</p></td>
</tr>
<tr class="odd">
<td><p>Note</p></td>
<td><p>Note</p></td>
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
<th><p>From Table: DEL_HRMLeaveType</p></th>
<th><p>To Table: HcmEmploymentLeave</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MappingRecId</p></td>
<td><p>LeaveType</p></td>
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
<th><p>From Table: HcmEmployment</p></th>
<th><p>To Table: HcmEmploymentLeave</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Employment</p></td>
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
<td><p>HcmEmploymentLeave</p></td>
<td><p>*</p></td>
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
<td><p>DEL_HRMEmplLeave</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

