---
title: ReleaseUpdateTransformDB50_Basic.updateEmplTablePreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.updateEmplTablePreProcessing Upgrade Script
ms:assetid: 84af3844-9a69-a4d8-3409-ff6a65a59a04
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686008(v=AX.60)
ms:contentKeyID: 49709459
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.updateEmplTablePreProcessing Upgrade Script 


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
<td><p>updateEmplTablePreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Party field in the EmplTable table and creates data in the HCMWorker and HCMEmployment tables from data in the EmplTable table.</p></td>
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
<td><p>EmplTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to convert the partyId field to the new party field for Microsoft Dynamics AX 2012. The party in the EmplTable will be kept as a reference to the DirPartyTable record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: EmplTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PartyId</p></td>
<td><p>Party</p></td>
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
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: HCMWorker</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>emplId</p></td>
<td><p>PersonnelNumber</p></td>
</tr>
<tr class="even">
<td><p>Party</p></td>
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
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: HCMEmployment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dataAreaId</p></td>
<td><p>LegalEnitiy</p></td>
</tr>
<tr class="even">
<td><p>dimension</p></td>
<td><p>DefaultDimension</p></td>
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
<th><p>From Table: HRMPartyEmployeeRelationship</p></th>
<th><p>To Table: HCMEmployment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EmployeeType</p></td>
<td><p>EmploymentType</p></td>
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
<td><p>EmplTable</p></td>
<td><p>Party</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>HCMWorker</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>HCMEmployment</p></td>
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
<td><p>EmplTable</p></td>
<td><p>PartyId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

