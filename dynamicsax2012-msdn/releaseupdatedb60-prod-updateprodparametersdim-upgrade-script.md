---
title: ReleaseUpdateDB60_Prod.updateProdParametersDim Upgrade Script
TOCTitle: ReleaseUpdateDB60_Prod.updateProdParametersDim Upgrade Script
ms:assetid: ee5837e7-9396-76da-8adf-52d663e74cba
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719967(v=AX.60)
ms:contentKeyID: 49712039
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Prod.updateProdParametersDim Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateProdParametersDim</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the AccountCostingScrap field to LedgerDimension field in the ProdParametersDim table.</p></td>
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
<td><p>Production</p></td>
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
<td><p>ProdParametersDim</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProdParametersDim</p></th>
<th><p>To Table: ProdParametersDim</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountCostingScrap</p></td>
<td><p>LedgerDimension</p></td>
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
<td><p>ProdParametersDim</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
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
<td><p>ProdParametersDim</p></td>
<td><p>AccountCostingScrap</p></td>
</tr>
</tbody>
</table>

  


