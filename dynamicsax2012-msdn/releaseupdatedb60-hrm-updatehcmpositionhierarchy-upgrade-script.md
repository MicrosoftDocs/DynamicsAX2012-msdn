---
title: ReleaseUpdateDB60_HRM.updateHcmPositionHierarchy Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmPositionHierarchy Upgrade Script
ms:assetid: 7acae235-c0fa-55b7-8ec8-fd815c38209a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719437(v=AX.60)
ms:contentKeyID: 49709228
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmPositionHierarchy Upgrade Script 


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
<td><p>updateHcmPositionHierarchy</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts data into the HcmPositionHierarchy table from the HRPPartyPositionTableRelationship table.</p></td>
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
<td><p>HcmPositionHierarchy</p></td>
</tr>
<tr class="even">
<td><p>HRPPartyPositionTableRelationship</p></td>
</tr>
<tr class="odd">
<td><p>HRPPartyJobTableRelationship</p></td>
</tr>
<tr class="even">
<td><p>HcmPosition</p></td>
</tr>
<tr class="odd">
<td><p>HcmPositionHierarchyType</p></td>
</tr>
</tbody>
</table>


## Remarks

1.  The Position field, which holds the record ID from the HcmPosition table, replaces the PositionId field.

2.  The ParentPosition field, which holds the record ID from the HcmPosition table, replaces the ReportsToPosition field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRPPartyPositionTableRelationship</p></th>
<th><p>To Table: HcmPositionHierarchy</p></th>
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
<td><p>HcmPositionHierarchy</p></td>
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
<td><p>HRPPartyPositionTableRelationship</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


