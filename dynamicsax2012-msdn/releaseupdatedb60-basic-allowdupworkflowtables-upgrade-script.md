---
title: ReleaseUpdateDB60_Basic.allowDupWorkflowTables Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupWorkflowTables Upgrade Script
ms:assetid: d15b90fc-0094-6df8-5724-fcaee6b1f1ac
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686928(v=AX.60)
ms:contentKeyID: 49711377
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupWorkflowTables Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupWorkflowTables</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This upgrade script removes the unique indexes on the workflow and alerts tables to allow duplicate IDs.</p></td>
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
<td><p>WorkflowElementTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowStepTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowMessageText</p></td>
</tr>
<tr class="even">
<td><p>WorkflowVersionTableNotes</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionTable</p></td>
</tr>
<tr class="even">
<td><p>EventRule</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleData</p></td>
</tr>
<tr class="even">
<td><p>EventRuleField</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleIgnore</p></td>
</tr>
<tr class="even">
<td><p>EventRuleRel</p></td>
</tr>
<tr class="odd">
<td><p>EventRuleRelData</p></td>
</tr>
</tbody>
</table>


## Remarks

In Microsoft Dynamics AX 2009, all workflow and alert rule tables were bound by company. In Microsoft Dynamics AX 2012 these tables are global. As a consequence, there will be duplicate IDs in the Microsoft Dynamics AX 2012 tables that will get created during the bulk copy from the source system to the target system. This script will remove the unique indexes on these tables thereby allowing existence of duplicate IDs.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

