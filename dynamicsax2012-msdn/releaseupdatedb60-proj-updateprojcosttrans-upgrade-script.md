---
title: ReleaseUpdateDB60_Proj.updateProjCostTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjCostTrans Upgrade Script
ms:assetid: d34e5911-b4ae-95db-6635-43107407fc2d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686996(v=AX.60)
ms:contentKeyID: 49711445
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjCostTrans Upgrade Script 


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
<td><p>updateProjCostTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the new transaction cost and sales amount tables.</p></td>
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
<td><p>ProjCostTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjCostTransCost</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostTransSale</p></td>
</tr>
</tbody>
</table>


## Remarks

A project transaction can now support multiple cost and sales amounts. For example, a project transaction can be billed to multiple customers. To support multiple cost and sales amounts, another level of tables were created. For the expense transaction type, the ProjCostTransCost and ProjCostTransSale tables are the new tables that were added.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjCostTrans</p></th>
<th><p>To Table: ProjCostTransCost</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TransId</p></td>
<td><p>TransId</p></td>
</tr>
<tr class="even">
<td><p>TransDate</p></td>
<td><p>LedgerTransdate</p></td>
</tr>
<tr class="odd">
<td><p>DEL_CostPrice</p></td>
<td><p>CostPrice</p></td>
</tr>
<tr class="even">
<td><p>TotalCostAmountCur</p></td>
<td><p>LineAmount</p></td>
</tr>
<tr class="odd">
<td><p>DEL_LedgerStatusCost</p></td>
<td><p>LedgerStatusCost</p></td>
</tr>
<tr class="even">
<td><p>DEL_TransStatus</p></td>
<td><p>TransStatus</p></td>
</tr>
<tr class="odd">
<td><p>DEL_WIPPeriod</p></td>
<td><p>WIPPeriod</p></td>
</tr>
<tr class="even">
<td><p>DEL_CostAmountLedger</p></td>
<td><p>CostAmountLedger</p></td>
</tr>
<tr class="odd">
<td><p>DEL_CostPriceCurrency</p></td>
<td><p>CostPriceCurrency</p></td>
</tr>
<tr class="even">
<td><p>DefaultDimension</p></td>
<td><p>DefaultDimension</p></td>
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
<th><p>From Table: ProjCostTrans</p></th>
<th><p>To Table: ProjCostTransSale</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TransId</p></td>
<td><p>TransId</p></td>
</tr>
<tr class="even">
<td><p>TransDate</p></td>
<td><p>LedgerTransdate</p></td>
</tr>
<tr class="odd">
<td><p>DEL_SalesPrice</p></td>
<td><p>SalesPrice</p></td>
</tr>
<tr class="even">
<td><p>TotalSalesAmountCur</p></td>
<td><p>LineAmount</p></td>
</tr>
<tr class="odd">
<td><p>DEL_LedgerSalesPosted</p></td>
<td><p>LedgerSalesPosted</p></td>
</tr>
<tr class="even">
<td><p>DEL_LedgerSalesAmount</p></td>
<td><p>LedgerSalesAmount</p></td>
</tr>
<tr class="odd">
<td><p>DEL_TransStatus</p></td>
<td><p>TransStatus</p></td>
</tr>
<tr class="even">
<td><p>DefaultDimension</p></td>
<td><p>DefaultDimension</p></td>
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
<td><p>ProjCostTrans</p></td>
<td><p>TotalCostAmountCur</p></td>
<td><p>ProjTotalCostAmount</p></td>
</tr>
<tr class="even">
<td><p>ProjCostTrans</p></td>
<td><p>TotalSalesAmountCur</p></td>
<td><p>ProjTotalSalesAmount</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostTransCost</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>ProjCostTransSale</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>ProjCostTrans</p></td>
<td><p>DEL_CostPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjCostTrans</p></td>
<td><p>DEL_LedgerStatusCost</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostTrans</p></td>
<td><p>DEL_WIPPeriod</p></td>
</tr>
<tr class="even">
<td><p>ProjCostTrans</p></td>
<td><p>DEL_CostAmountLedger</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostTrans</p></td>
<td><p>DEL_CostPriceCurrency</p></td>
</tr>
<tr class="even">
<td><p>ProjCostTrans</p></td>
<td><p>DEL_SalesPrice</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostTrans</p></td>
<td><p>DEL_LedgerSalesPosted</p></td>
</tr>
<tr class="even">
<td><p>ProjCostTrans</p></td>
<td><p>DEL_LedgerSalesAmount</p></td>
</tr>
<tr class="odd">
<td><p>ProjCostTrans</p></td>
<td><p>DEL_TransStatus</p></td>
</tr>
</tbody>
</table>

  


