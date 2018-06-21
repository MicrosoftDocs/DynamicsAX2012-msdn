---
title: ReleaseUpdateDB60_KM.updateKMKnowledgeCollectorPlanningTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_KM.updateKMKnowledgeCollectorPlanningTable Upgrade Script
ms:assetid: 0b8c1182-1c69-ab7b-4ad8-5800952ab2b5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735651(v=AX.60)
ms:contentKeyID: 49706562
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_KM.updateKMKnowledgeCollectorPlanningTable Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_KM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateKMKnowledgeCollectorPlanningTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ResponsibleWorker field of the KMKnowledgeCollectorPlanningTable table with the corresponding value from the RecId field of the HcmWorker table.</p></td>
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
<td><p>KMKnowledgeCollectorPlanningTable</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
</tr>
<tr class="odd">
<td><p>HcmWorker</p></td>
</tr>
</tbody>
</table>


## Remarks

The ResponsibleWorker field, which has the RecId value from the HcmWorker table, replaces the Responsible field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: KMKnowledgeCollectorPlanningTable</p></th>
<th><p>To Table: KMKnowledgeCollectorPlanningTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Responsible</p></td>
<td><p>ResponsibleWorker</p></td>
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
<td><p>KMKnowledgeCollectorPlanningTable</p></td>
<td><p>ResponsibleWorker</p></td>
<td><p>HcmWorkerRecId</p></td>
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
<td><p>*</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: KMKnowledgeCollectorPlanningTable</p></th>
<th><p>New Table Name: KMKnowledgeCollectorPlanningTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>Responsible</p></td>
<td><p>DEL_Responsible</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

