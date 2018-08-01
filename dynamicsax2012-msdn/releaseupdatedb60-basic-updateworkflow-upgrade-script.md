---
title: ReleaseUpdateDB60_Basic.updateWorkflow Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateWorkflow Upgrade Script
ms:assetid: 3187535f-b87b-3eda-62fe-e1edd44c4d3f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736094(v=AX.60)
ms:contentKeyID: 49707508
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateWorkflow Upgrade Script 


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
<td><p>updateWorkflow</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the version for all records in the SysWorkflowTable table toMicrosoft Dynamics AX 2009. This will let runtime know that these are in-flight Microsoft Dynamics AX 2009 workflow instances.</p></td>
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
<td><p>SysWorkflowTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The SysWorkflowTable represents running workflows. During upgrade, if there are any records in this table ,it indicates in-flight workflow instances. After the upgrade is complete, there could be new Microsoft Dynamics AX 2012 workflow instances in this table. By setting the version to Microsoft Dynamics AX 2009 during the upgrade, runtime will know which running instances were triggered from the Microsoft Dynamics AX 2009 configurations and after, and follow a different code path to complete executing the workflow to completion.

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
<td><p>SysWorkflowTable</p></td>
<td><p>Version</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


