---
title: ReleaseUpdateDB60_HRM.updateHcmDiscussion Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmDiscussion Upgrade Script
ms:assetid: b04077b4-2389-c2b8-0f8a-004b33cb88a9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686590(v=AX.60)
ms:contentKeyID: 49710542
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmDiscussion Upgrade Script [AX 2012]


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
<td><p>updateHcmDiscussion</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmDiscussion table from the DEL_HRMInterviewTable table.</p></td>
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
<td><p>HcmDiscussion</p></td>
</tr>
<tr class="even">
<td><p>DEL_HRMInterviewTable</p></td>
</tr>
<tr class="odd">
<td><p>DEL_EmplTable</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
</tr>
<tr class="odd">
<td><p>DEL_HRMInterviewType</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending the DataAreaId field to the HrmInterviewId field of the DEL\_HRMInterviewTable table to create new, unique identifiers for the HcmDiscussion table when multiple companies exist. If only one company exists, the DataAreaId field will not be appended. The Worker field in the HcmDiscussion table is the foreign key to the HcmWorker table and is initialized by finding the worker that corresponds to the EmplId field of the DEL\_HRMInterviewTable table. The Goal field in the HcmDiscussion table is the foreign key to the HcmGoal table. The DiscussionType field in the HcmDiscussion table is the foreign key to the HcmDiscussionType table. The data in the HcmDiscussion table is created by this script. The DEL\_HRMInterviewTable, DEL\_EmplTable, HcmWorker, and DEL\_HRMInterviewType tables are read, but not updated, by this script.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMInterviewTable</p></th>
<th><p>To Table: HcmDiscussion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>hrmInterviewId</p></td>
<td><p>DiscussionId</p></td>
</tr>
<tr class="even">
<td><p>description</p></td>
<td><p>Description</p></td>
</tr>
<tr class="odd">
<td><p>hrmInterviewTypeId</p></td>
<td><p>DiscussionType</p></td>
</tr>
<tr class="even">
<td><p>interviewDate</p></td>
<td><p>DiscussionDate</p></td>
</tr>
<tr class="odd">
<td><p>interviewTime</p></td>
<td><p>DiscussionTime</p></td>
</tr>
<tr class="even">
<td><p>emplId</p></td>
<td><p>Worker</p></td>
</tr>
<tr class="odd">
<td><p>status</p></td>
<td><p>Status</p></td>
</tr>
<tr class="even">
<td><p>responsible</p></td>
<td><p>ResponsibleWorker</p></td>
</tr>
<tr class="odd">
<td><p>GoalId</p></td>
<td><p>Goal</p></td>
</tr>
<tr class="even">
<td><p>interviewPlace</p></td>
<td><p>DiscussionPlace</p></td>
</tr>
<tr class="odd">
<td><p>interviewEndTime</p></td>
<td><p>DiscussionEndTime</p></td>
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
<td><p>HcmDiscussion</p></td>
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
<td><p>HRMInterviewTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

