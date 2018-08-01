---
title: ReleaseUpdateTransformDB50_Basic.updateDirPartyRelationshipPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.updateDirPartyRelationshipPreProcessing Upgrade Script
ms:assetid: da0ef0be-a4b1-2ea9-38cf-a0e41ae6606c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737158(v=AX.60)
ms:contentKeyID: 49711602
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.updateDirPartyRelationshipPreProcessing Upgrade Script [AX 2012]


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
<td><p>updateDirPartyRelationshipPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ParentParty and ChildParty fields in the DirPartyRelationship table and removes duplicate records.</p></td>
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
<td><p>DirPartyRelationship</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to convert the ParentPartyId and ChildPartyId fields to the new party fields for Microsoft Dynamics AX 2012. The ParentParty and ChildParty fields in the DirPartyRelationship table will be kept as a reference to the DirPartyTable record. This script also removes the duplicate records as the DirPartyRelationship table becomes global table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DirPartyRelationship</p></th>
<th><p>To Table: DirPartyRelationship</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ParentPartyId</p></td>
<td><p>ParentParty</p></td>
</tr>
<tr class="even">
<td><p>ChildPartyId</p></td>
<td><p>ChildParty</p></td>
</tr>
<tr class="odd">
<td><p>ValidFromDateTime</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="even">
<td><p>ValidToDateTime</p></td>
<td><p>ValidTo</p></td>
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
<td><p>DirPartyRelationship</p></td>
<td><p>ParentParty</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirPartyRelationship</p></td>
<td><p>ChildParty</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>DirPartyRelationship</p></td>
<td><p>ValidFrom</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DirPartyRelationship</p></td>
<td><p>ValidTo</p></td>
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
<td><p>DirPartyRelationship</p></td>
<td><p>ParentPartyId</p></td>
</tr>
<tr class="even">
<td><p>DirPartyRelationship</p></td>
<td><p>ChildPartyId</p></td>
</tr>
<tr class="odd">
<td><p>DirPartyRelationship</p></td>
<td><p>ValidFromDateTime</p></td>
</tr>
<tr class="even">
<td><p>DirPartyRelationship</p></td>
<td><p>ValidToDateTime</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

