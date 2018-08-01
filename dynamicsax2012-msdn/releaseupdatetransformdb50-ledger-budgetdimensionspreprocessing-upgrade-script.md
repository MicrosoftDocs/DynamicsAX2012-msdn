---
title: ReleaseUpdateTransformDB50_Ledger.budgetDimensionsPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.budgetDimensionsPreProcessing Upgrade Script
ms:assetid: ef6648ef-6c9e-ef2c-a102-4aa0fa4e1d90
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720025(v=AX.60)
ms:contentKeyID: 49712077
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.budgetDimensionsPreProcessing Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>budgetDimensionsPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the LedgerBudget table to the BudgetPrimaryLedgerDimensionAttribute table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>BudgetPrimaryLedgerDimensionAttribute</p></td>
</tr>
</tbody>
</table>


## Remarks

Inserts records into the BudgetPrimaryLedgerDimensionAttribute table for the unique dimensions in use in the LedgerBudget table and adds them to the account structure.

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
<td><p>BudgetPrimaryLedgerDimensionAttribute</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


