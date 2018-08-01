---
title: ReleaseUpdateDB60_Proj.updateProjItemTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjItemTrans Upgrade Script
ms:assetid: 6c0b1575-3512-f0d2-99d8-ccf2671b11fe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685685(v=AX.60)
ms:contentKeyID: 49708886
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjItemTrans Upgrade Script [AX 2012]


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
<td><p>updateProjItemTrans</p></td>
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
<td><p>ProjItemTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjItemTransCost</p></td>
</tr>
<tr class="odd">
<td><p>ProjItemTransSale</p></td>
</tr>
</tbody>
</table>


## Remarks

A project transaction can now support multiple cost and sales amount. For example, a project transaction can be billed to multiple customers. To support multiple cost and sales amount, another level of tables was created. For the item transaction type, the ProjItemTransCost and ProjItemTransSale tables are the new tables that were added.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjItemTrans</p></th>
<th><p>To Table: ProjItemTransCost</p></th>
</tr>
</thead>
<tbody>
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


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjItemTrans</p></th>
<th><p>To Table: ProjItemTransSale</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ProjTransId</p></td>
<td><p>ProjTransId</p></td>
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
<td><p>DEL_LedgerSalesPosted</p></td>
<td><p>LedgerSalesPosted</p></td>
</tr>
<tr class="odd">
<td><p>DEL_LedgerSalesAmount</p></td>
<td><p>LedgerSalesAmount</p></td>
</tr>
<tr class="even">
<td><p>DEL_TransStatus</p></td>
<td><p>TransStatus</p></td>
</tr>
<tr class="odd">
<td><p>DEL_LineAmount</p></td>
<td><p>LineAmount</p></td>
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
<td><p>ProjItemTrans</p></td>
<td><p>TotalCostAmountCur</p></td>
<td><p>ProjTotalCostAmount</p></td>
</tr>
<tr class="even">
<td><p>ProjItemTrans</p></td>
<td><p>TotalSalesAmountCur</p></td>
<td><p>ProjTotalSalesAmount</p></td>
</tr>
<tr class="odd">
<td><p>ProjItemTransCost</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>ProjItemTransSale</p></td>
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
<td><p>ProjItemTrans</p></td>
<td><p>DEL_SalesPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjItemTrans</p></td>
<td><p>DEL_LedgerSalesPosted</p></td>
</tr>
<tr class="odd">
<td><p>ProjItemTrans</p></td>
<td><p>DEL_LedgerSalesAmount</p></td>
</tr>
<tr class="even">
<td><p>ProjItemTrans</p></td>
<td><p>DEL_LineAmount</p></td>
</tr>
<tr class="odd">
<td><p>ProjItemTrans</p></td>
<td><p>DEL_TransStatus</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

