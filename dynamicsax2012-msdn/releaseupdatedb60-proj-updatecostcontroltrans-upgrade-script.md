---
title: ReleaseUpdateDB60_Proj.updateCostControlTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateCostControlTrans Upgrade Script
ms:assetid: 13bbd4ad-6b43-edf5-64a3-5acfb998f469
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718491(v=AX.60)
ms:contentKeyID: 49706776
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateCostControlTrans Upgrade Script [AX 2012]


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
<td><p>updateCostControlTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Moves the cost information from the CostControlTransCommittedCost table to the CostControlTransCommittedCostDetail table. In order to support a one to many relationship, one committed cost could have multiple cost lines for different funding sources.</p></td>
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
<td><p>CostControlTransCommittedCost</p></td>
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
<th><p>From Table: CostControlTransCommittedCost</p></th>
<th><p>To Table: CostControlTransCommittedCostDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amount</p></td>
<td><p>Amount</p></td>
</tr>
<tr class="even">
<td><p>AmountMST</p></td>
<td><p>AmountMST</p></td>
</tr>
<tr class="odd">
<td><p>WIPPeriod</p></td>
<td><p>WIPPeriod</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

