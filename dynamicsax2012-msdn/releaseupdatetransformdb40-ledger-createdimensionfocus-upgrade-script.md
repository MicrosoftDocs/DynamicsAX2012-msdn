---
title: ReleaseUpdateTransformDB40_Ledger.createDimensionFocus Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.createDimensionFocus Upgrade Script
ms:assetid: 032bcf54-4a53-3e58-c64e-4d1f13126939
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684664(v=AX.60)
ms:contentKeyID: 49706361
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.createDimensionFocus Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createDimensionFocus</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the dimension focus records.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>DimensionSetTable</p></td>
</tr>
<tr class="even">
<td><p>DimensionPriorityTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The information from the DimensionSetTable and the DimensionPriorityTable will be processed and added to the DimensionHierarchy, DimensionHierarchyLevel, and DimensionFocusState tables.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DimensionSetTable</p></th>
<th><p>To Table: DimensionHierarchy</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetId</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>Description</p></td>
<td><p>Description</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

