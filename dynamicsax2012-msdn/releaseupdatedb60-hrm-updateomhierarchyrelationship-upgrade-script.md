---
title: ReleaseUpdateDB60_HRM.updateOMHierarchyRelationship Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateOMHierarchyRelationship Upgrade Script
ms:assetid: 42765400-f00a-3266-8685-cf66a68ae0fc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718852(v=AX.60)
ms:contentKeyID: 49707896
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateOMHierarchyRelationship Upgrade Script 


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
<td><p>updateOMHierarchyRelationship</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates the existing records in the DirPartyRelationship table that relate departments to each other into the new OMHierarchyRelationship table, and then removes the old records after completion.</p></td>
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
<td><p>DirPartyRelationship</p></td>
</tr>
<tr class="even">
<td><p>DirRelationshipTypeTable</p></td>
</tr>
<tr class="odd">
<td><p>OMHierarchyPurpose</p></td>
</tr>
<tr class="even">
<td><p>OMHierarchyRelationship</p></td>
</tr>
<tr class="odd">
<td><p>OMHierarchyType</p></td>
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
<th><p>From Table: DirPartyRelationship</p></th>
<th><p>To Table: OMHierarchyRelationship</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ChildParty</p></td>
<td><p>ChildOrganization</p></td>
</tr>
<tr class="even">
<td><p>ParentParty</p></td>
<td><p>ParentOrganization</p></td>
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

  


