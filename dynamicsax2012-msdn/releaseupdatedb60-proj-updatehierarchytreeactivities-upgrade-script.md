---
title: ReleaseUpdateDB60_Proj.updateHierarchyTreeActivities Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateHierarchyTreeActivities Upgrade Script
ms:assetid: 39d50b2d-e4b4-08bc-75ac-b6d8ccbeece2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685246(v=AX.60)
ms:contentKeyID: 49707698
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateHierarchyTreeActivities Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHierarchyTreeActivities</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates an activity for hierarchy elements that are of type node. Hierarchies that are created based on templates will also be updated to reflect changes in how template references are tracked.</p></td>
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
<td><p>Basic</p></td>
</tr>
<tr class="even">
<td><p>Project</p></td>
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
<td><p>HierarchyTreeTable</p></td>
</tr>
<tr class="even">
<td><p>smmActivities</p></td>
</tr>
<tr class="odd">
<td><p>smmActivityParentLinkTable</p></td>
</tr>
<tr class="even">
<td><p>ProjActivity</p></td>
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
<th><p>From Table: HierarchyTreeTable</p></th>
<th><p>To Table: HierarchyTreeTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>TemplateRecId</p></td>
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
<td><p>HierarchyTreeTable</p></td>
<td><p>TemplateRecId</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>

  


