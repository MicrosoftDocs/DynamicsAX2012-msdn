---
title: ReleaseUpdateDB60_Proj.updateProjRevenueTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjRevenueTrans Upgrade Script
ms:assetid: dfcab846-4313-4086-9d37-46d44f56d616
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737281(v=AX.60)
ms:contentKeyID: 49711723
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjRevenueTrans Upgrade Script 


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
<td><p>updateProjRevenueTrans</p></td>
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
<td><p>ProjRevenueTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueTransSale</p></td>
</tr>
</tbody>
</table>


## Remarks

A project transaction can now support multiple cost and sales amount. For example, a project transaction can be billed to multiple customers. To support multiple cost and sales amount, another level of tables was created. For the fee transaction type, the ProjRevenueTransSale is the new table that was added.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjRevenueTrans</p></th>
<th><p>To Table: ProjRevenueTransSale</p></th>
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
<td><p>DEL_WIPPeriod</p></td>
<td><p>WIPPeriod</p></td>
</tr>
<tr class="odd">
<td><p>DEL_WIPType</p></td>
<td><p>WIPType</p></td>
</tr>
<tr class="even">
<td><p>DEL_ControlVersion</p></td>
<td><p>ControlVersion</p></td>
</tr>
<tr class="odd">
<td><p>DEL_ControlId</p></td>
<td><p>ControlId</p></td>
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
<td><p>ProjRevenueTrans</p></td>
<td><p>TotalSalesAmountCur</p></td>
<td><p>ProjTotalSalesAmount</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueTransSale</p></td>
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
<td><p>ProjRevenueTrans</p></td>
<td><p>DEL_SalesPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueTrans</p></td>
<td><p>DEL_LedgerSalesPosted</p></td>
</tr>
<tr class="odd">
<td><p>ProjRevenueTrans</p></td>
<td><p>DEL_LedgerSalesAmount</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueTrans</p></td>
<td><p>DEL_TransStatus</p></td>
</tr>
<tr class="odd">
<td><p>ProjRevenueTrans</p></td>
<td><p>DEL_WIPPeriod</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueTrans</p></td>
<td><p>DEL_WIPType</p></td>
</tr>
<tr class="odd">
<td><p>ProjRevenueTrans</p></td>
<td><p>DEL_ControlVersion</p></td>
</tr>
<tr class="even">
<td><p>ProjRevenueTrans</p></td>
<td><p>DEL_ControlId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

