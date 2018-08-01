---
title: ReleaseUpdateDB60_Proj.updateProjOnAccTrans Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjOnAccTrans Upgrade Script
ms:assetid: 176caf9a-5266-3751-be01-a5eda72c352c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718578(v=AX.60)
ms:contentKeyID: 49706862
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjOnAccTrans Upgrade Script 


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
<td><p>updateProjOnAccTrans</p></td>
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
<td><p>ProjOnAccTrans</p></td>
</tr>
<tr class="even">
<td><p>ProjOnAccTransSale</p></td>
</tr>
</tbody>
</table>


## Remarks

A project transaction can now support multiple cost and sales amount. For example, a project transaction can be billed to multiple customers. To support multiple cost and sales amount, another level of tables was created. For the on-account transaction type, the ProjOnAccTransSale table is the new table that was added.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjOnAccTrans</p></th>
<th><p>To Table: ProjOnAccTransSale</p></th>
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
<td><p>DEL_Amount</p></td>
<td><p>Amount</p></td>
</tr>
<tr class="even">
<td><p>DEL_WIPPeriod</p></td>
<td><p>WIPPeriod</p></td>
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
<td><p>ProjOnAccTrans</p></td>
<td><p>TotalSalesAmountCur</p></td>
<td><p>ProjTotalSalesAmount</p></td>
</tr>
<tr class="even">
<td><p>ProjOnAccTransSale</p></td>
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
<td><p>ProjOnAccTrans</p></td>
<td><p>DEL_Amount</p></td>
</tr>
<tr class="even">
<td><p>ProjOnAccTrans</p></td>
<td><p>DEL_WIPPeriod</p></td>
</tr>
<tr class="odd">
<td><p>ProjOnAccTrans</p></td>
<td><p>DEL_LedgerSalesAmount</p></td>
</tr>
<tr class="even">
<td><p>ProjOnAccTrans</p></td>
<td><p>DEL_TransStatus</p></td>
</tr>
</tbody>
</table>

  


