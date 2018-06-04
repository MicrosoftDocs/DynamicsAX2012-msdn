---
title: ReleaseUpdateTransformDB50_Basic.updateDirPersonPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.updateDirPersonPreProcessing Upgrade Script
ms:assetid: 8ea05dde-ab06-cbb8-863a-ca354f629b8a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736514(v=AX.60)
ms:contentKeyID: 49709703
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.updateDirPersonPreProcessing Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateDirPersonPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data in the DirPartyTable table into the DirPerson table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>DirPartyTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to transform the data in the DirPartyTable table, which has the Person type, into the DirPerson table in the new global address book model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DirPartyTable</p></th>
<th><p>To Table: DirPerson</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
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
<th><p>From Table: DirPartyTable</p></th>
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
<tr class="even">
<td><p>RecId</p></td>
<td><p>Person</p></td>
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
<th><p>From Table: dirPersonPartyDetail</p></th>
<th><p>To Table: DirPerson</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Prefix</p></td>
<td><p>ProfessionalTitle</p></td>
</tr>
<tr class="even">
<td><p>ProfessionalSuffix</p></td>
<td><p>ProfressionalSuffix</p></td>
</tr>
<tr class="odd">
<td><p>Initials</p></td>
<td><p>Initials</p></td>
</tr>
<tr class="even">
<td><p>ChildrenNames</p></td>
<td><p>ChildrenNames</p></td>
</tr>
<tr class="odd">
<td><p>BirthDate</p></td>
<td><p>BirthDate</p></td>
</tr>
<tr class="even">
<td><p>MaritalStatus</p></td>
<td><p>MaritalStatus</p></td>
</tr>
<tr class="odd">
<td><p>AnniversaryDate</p></td>
<td><p>AnniversaryDate</p></td>
</tr>
<tr class="even">
<td><p>Hobbies</p></td>
<td><p>Hobbies</p></td>
</tr>
<tr class="odd">
<td><p>Gender</p></td>
<td><p>Gender</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
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
<td><p>DirPerson</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirPersonName</p></td>
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
<td><p>dirPersonPartyDetail</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

