---
title: ReleaseUpdateDB60_Trv.updateTrvExpTransProj Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvExpTransProj Upgrade Script
ms:assetid: 7b957dbb-7306-cf8e-4306-d2f6d4e70fdd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719451(v=AX.60)
ms:contentKeyID: 49709241
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvExpTransProj Upgrade Script 


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
<td><p>updateTrvExpTransProj</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies the ActivityNumber field from the DEL_TrvExpTrans_Proj table to the TrvExpTrans table.</p></td>
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
<td><p>DEL_TrvExpTrans_Proj</p></td>
</tr>
<tr class="even">
<td><p>TrvExpTrans</p></td>
</tr>
<tr class="odd">
<td><p>ProjectAccountingDistribution</p></td>
</tr>
</tbody>
</table>


## Remarks

Creates project distributions for the TrvExpTrans table by using the DEL\_TrvExpTrans\_proj table. Copies the ActivityNumber field from DEL\_TrvExpTrans\_proj table to the TrvExpTrans table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_TrvExpTrans_Proj</p></th>
<th><p>To Table: TrvExpTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ActivityNumber</p></td>
<td><p>ProjActivityNumber</p></td>
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
<td><p>TrvExpTrans</p></td>
<td><p>ProjActivityNumber</p></td>
<td><p>ProjActivityNumber</p></td>
</tr>
</tbody>
</table>

  


