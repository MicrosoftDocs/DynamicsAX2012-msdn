---
title: ReleaseUpdateDB60_Proj.updateFundingRuleAlloc Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateFundingRuleAlloc Upgrade Script
ms:assetid: 3117c2a3-39f8-ef6c-48c5-04fbe7112570
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736080(v=AX.60)
ms:contentKeyID: 49707494
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateFundingRuleAlloc Upgrade Script 


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
<td><p>updateFundingRuleAlloc</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the default funding allocations for the contract funding rules. Each rule must have one-hundred percent allocation to the funding entities of the contract.</p></td>
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
<td><p>ProjFundingRule</p></td>
</tr>
<tr class="even">
<td><p>ProjFundingRuleAllocation</p></td>
</tr>
<tr class="odd">
<td><p>ProjFundingSource</p></td>
</tr>
</tbody>
</table>


## Remarks

Creates a single row for each funding rule. The record will contain a foreign key reference to the rule, a foreign key reference to the funding entity on the contract, an allocation percentage of one-hundred, and the default rounding account set to true.

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
<td><p>ProjFundingRuleAllocation</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

