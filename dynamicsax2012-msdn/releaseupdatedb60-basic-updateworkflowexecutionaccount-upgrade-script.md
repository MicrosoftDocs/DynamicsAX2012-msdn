---
title: ReleaseUpdateDB60_Basic.updateWorkflowExecutionAccount Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateWorkflowExecutionAccount Upgrade Script
ms:assetid: 5352ec5b-27aa-f514-ce67-f0ae406d4bd2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736116(v=AX.60)
ms:contentKeyID: 49708292
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateWorkflowExecutionAccount Upgrade Script 


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
<td><p>updateWorkflowExecutionAccount</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The workflow execution account should be assigned the SysAdmin role during upgrade.</p></td>
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
<td><p>SecurityUserRole</p></td>
</tr>
</tbody>
</table>


## Remarks

The script gets the WorkflowExecutionAccount user ID from the Workflow parameters and checks to see if this user is part of the SysAdmin role. If not, it assigns this user to that role.

  


