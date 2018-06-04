---
title: ReleaseUpdateDB60_Basic.validateWorkflow Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.validateWorkflow Upgrade Script
ms:assetid: 02555f8d-cd72-6a62-cf07-e008d7da75f1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684643(v=AX.60)
ms:contentKeyID: 49706344
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.validateWorkflow Upgrade Script 


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
<td><p>validateWorkflow</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Checks for active instances of workflows and throws an error message if any are present. If there are no active instances present then it deletes all workflow configurations that should not be upgraded.</p></td>
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
<td><p>DEL_WorkflowConfigurationTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowElementTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowConfigurationTableNotes</p></td>
</tr>
<tr class="even">
<td><p>ExpressionTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowStepTable</p></td>
</tr>
<tr class="even">
<td><p>WorkflowMessageText</p></td>
</tr>
<tr class="odd">
<td><p>WorkflowSubworkflowTable</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

