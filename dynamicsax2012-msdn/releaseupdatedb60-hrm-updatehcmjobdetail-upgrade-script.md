---
title: ReleaseUpdateDB60_HRM.updateHcmJobDetail Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmJobDetail Upgrade Script
ms:assetid: 82486757-8153-5d23-018b-592c3c114be4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685948(v=AX.60)
ms:contentKeyID: 49709401
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmJobDetail Upgrade Script 


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
<td><p>updateHcmJobDetail</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts data into the HcmJobDetail table from the HRPPartyJobTableRelationship table.</p></td>
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
<td><p>HcmJobDetail</p></td>
</tr>
<tr class="even">
<td><p>HRPPartyJobTableRelationship</p></td>
</tr>
<tr class="odd">
<td><p>HcmJob</p></td>
</tr>
<tr class="even">
<td><p>HRMCompJobFunction</p></td>
</tr>
<tr class="odd">
<td><p>HRMCompJobType</p></td>
</tr>
<tr class="even">
<td><p>HcmCompensationLevel</p></td>
</tr>
<tr class="odd">
<td><p>HcmTitle</p></td>
</tr>
<tr class="even">
<td><p>HcmSurveyCompany</p></td>
</tr>
<tr class="odd">
<td><p>HcmJobDetail</p></td>
</tr>
</tbody>
</table>


## Remarks

1.  The Job field, which holds a record ID from the HcmJob table, replaces the JobId field.

2.  The JobFunction field, which holds a record ID from the HcmJobFunction table, replaces the HrmCompJobFunctionId field.

3.  The JobType field, which holds record ID from the HcmJobType table, replaces the HrmCompJobTypeId field.

4.  The CompensationLevel field, which holds record ID from the HcmCompensationLevel table, replaces the HrmCompLevelId field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRPPartyJobTableRelationship</p></th>
<th><p>To Table: HcmJobDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<td><p>HcmJobDetail</p></td>
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
<td><p>HRPPartyJobTableRelationship</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

