---
title: ReleaseUpdateDB60_HRM.updateHRMAbsenceTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMAbsenceTable Upgrade Script
ms:assetid: 98f7aa2c-a02b-7936-54f9-507b3aeaaaf0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686256(v=AX.60)
ms:contentKeyID: 49709959
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMAbsenceTable Upgrade Script 


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
<td><p>updateHRMAbsenceTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the Worker, Worker_PostedBy, Worker_ApprovedBy, and Worker_RejectedBy fields in the HRMAbsenceTable table.</p></td>
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
<td><p>DirPerson</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
</tr>
<tr class="odd">
<td><p>HcmWorker</p></td>
</tr>
<tr class="even">
<td><p>HRMAbsenceTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Populates the Worker field in the HRMAbsenceTable table from the EmplId field in the HRMAbsenceTable table. Populates the Worker\_PostedBy field in the HRMAbsenceTable table from the PostedBy field in the HRMAbsenceTable table. Populates the Worker\_ApprovedBy field in the HRMAbsenceTable table from the ApprovedBy field in the HRMAbsenceTable table. Populates the Worker\_RejectedBy field in the HRMAbsenceTable table from the RejectedBy field in the HRMAbsenceTable table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMAbsenceTable</p></th>
<th><p>To Table: HRMAbsenceTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EmplId</p></td>
<td><p>Worker</p></td>
</tr>
<tr class="even">
<td><p>PostedBy</p></td>
<td><p>PostedBy</p></td>
</tr>
<tr class="odd">
<td><p>ApprovedBy</p></td>
<td><p>Worker_ApprovedBy</p></td>
</tr>
<tr class="even">
<td><p>RejectedBy</p></td>
<td><p>RejectedBy</p></td>
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
<td><p>HRMAbsenceTable</p></td>
<td><p>Worker</p></td>
<td><p>HcmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>PostedBy</p></td>
<td><p>HcmWorkerRecId</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Worker_ApprovedBy</p></td>
<td><p>HcmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>RejectedBy</p></td>
<td><p>HcmWorkerRecId</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: HRMAbsenceTable</p></th>
<th><p>New Table Name: HRMAbsenceTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>EmplId</p></td>
<td><p>DEL_EmplId</p></td>
</tr>
<tr class="odd">
<td><p>PostedBy</p></td>
<td><p>DEL_PostedBy</p></td>
</tr>
<tr class="even">
<td><p>Worker_ApprovedBy</p></td>
<td><p>DEL_Worker_ApprovedBy</p></td>
</tr>
<tr class="odd">
<td><p>RejectedBy</p></td>
<td><p>DEL_RejectedBy</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

