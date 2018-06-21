---
title: ReleaseUpdateTransformDB50_Lean.legalEntityUpdate Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Lean.legalEntityUpdate Upgrade Script
ms:assetid: a6d5d90d-117a-6acd-dbc9-12d057f08556
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736868(v=AX.60)
ms:contentKeyID: 49710299
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Lean.legalEntityUpdate Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Lean</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>legalEntityUpdate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates LegalEntity field in several tables that are based on the upgraded CompanyInfo record for the company where the PlanReference record was created.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Single user</p></td>
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
<td><p>Manufacture</p></td>
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
<td><p>PlanReference</p></td>
</tr>
<tr class="even">
<td><p>PlanActivity</p></td>
</tr>
<tr class="odd">
<td><p>KanbanFlow</p></td>
</tr>
<tr class="even">
<td><p>KanbanRule</p></td>
</tr>
<tr class="odd">
<td><p>Kanban</p></td>
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
<th><p>From Table: Shadow_CompanyInfo</p></th>
<th><p>To Table: PlanReference</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>LegalEntity</p></td>
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
<th><p>From Table: Shadow_CompanyInfo</p></th>
<th><p>To Table: PlanActivity</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>LegalEntity</p></td>
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
<th><p>From Table: Shadow_CompanyInfo</p></th>
<th><p>To Table: KanbanFlow</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>LegalEntity</p></td>
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
<th><p>From Table: Shadow_CompanyInfo</p></th>
<th><p>To Table: KanbanRule</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>LegalEntity</p></td>
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
<th><p>From Table: Shadow_CompanyInfo</p></th>
<th><p>To Table: Kanban</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DirPartyTableRecId</p></td>
<td><p>LegalEntity</p></td>
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
<td><p>PlanReference</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PlanActivity</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PlanPlanActivity</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Plan</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>KanbanFlow</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>KanbanRule</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Kanban</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

