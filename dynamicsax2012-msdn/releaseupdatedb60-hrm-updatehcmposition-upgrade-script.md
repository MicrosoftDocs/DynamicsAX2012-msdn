---
title: ReleaseUpdateDB60_HRM.updateHcmPosition Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPosition Upgrade Script
ms:assetid: 6b7e5603-f9bb-59e9-7b89-cc8ff45db877
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685692(v=AX.60)
ms:contentKeyID: 49708893
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPosition Upgrade Script 


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
<td><p>updateHcmPosition</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts data into the HcmPosition table from the HRPPartyPositionTable table.</p></td>
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
<td><p>HcmPosition</p></td>
</tr>
<tr class="even">
<td><p>HRPPartyPositionTable</p></td>
</tr>
<tr class="odd">
<td><p>HRPPartyPositionTableRelationship</p></td>
</tr>
<tr class="even">
<td><p>HRPPartyJobTableRelationship</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending value of the DataAreaId field to the PositionId field of the HRPPartyPositionTable table to create new, unique identifiers for the HcmPosition table when multiple companies exist. If only one company exists, the DataAreaId field will not be appended.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRPPartyPositionTable</p></th>
<th><p>To Table: HcmPosition</p></th>
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
<td><p>HcmPosition</p></td>
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
<td><p>HRPPartyPositionTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


