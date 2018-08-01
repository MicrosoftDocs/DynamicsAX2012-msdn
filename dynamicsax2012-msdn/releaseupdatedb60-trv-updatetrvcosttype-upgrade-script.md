---
title: ReleaseUpdateDB60_Trv.updateTrvCostType Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvCostType Upgrade Script
ms:assetid: ee2babc1-35d6-22f5-dfdb-b23e35adf90d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719963(v=AX.60)
ms:contentKeyID: 49712035
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvCostType Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateTrvCostType</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the new IsItemizationMandatory field value to true for the hotel expense categories.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>TrvCostType</p></td>
</tr>
</tbody>
</table>


## Remarks

For existing hotel expense categories the IsItemizationMandatory field in the TrvCostType table is set to true. For all other categories the field is set to false.

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
<td><p>TrvCostType</p></td>
<td><p>IsItemizationMandatory</p></td>
<td><p>NoYes</p></td>
</tr>
</tbody>
</table>

  


