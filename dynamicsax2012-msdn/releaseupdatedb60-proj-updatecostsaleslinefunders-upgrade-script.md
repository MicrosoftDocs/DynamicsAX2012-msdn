---
title: ReleaseUpdateDB60_Proj.updateCostSalesLineFunders Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateCostSalesLineFunders Upgrade Script
ms:assetid: 0cb07fa4-6a6c-6fd1-d1eb-38dde89976a8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735688(v=AX.60)
ms:contentKeyID: 49706595
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateCostSalesLineFunders Upgrade Script 


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
<td><p>updateCostSalesLineFunders</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates funding sources on cost and sales detail lines. The funding source that is associated with a line depends on the project contract.</p></td>
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
<td><p>ProjEmplTransCost</p></td>
</tr>
<tr class="even">
<td><p>ProjEmplTransSale</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostTransCost</p></td>
</tr>
<tr class="even">
<td><p>ProjCostTransSale</p></td>
</tr>
<tr class="odd">
<td><p>ProjItemTransCost</p></td>
</tr>
<tr class="even">
<td><p>ProjItemTransSale</p></td>
</tr>
<tr class="odd">
<td><p>ProjOnAccTransSale</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueTransSale</p></td>
</tr>
</tbody>
</table>

  


