---
title: ReleaseUpdateTransformDB50_Cust.commissionTransPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Cust.commissionTransPreUpgradeProcess Upgrade Script
ms:assetid: afeeef0b-4792-8432-cc5c-be9684823d2d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686593(v=AX.60)
ms:contentKeyID: 49710547
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Cust.commissionTransPreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>commissionTransPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the Dimension and EmplId fields to the DefaultDimension and Person fields in the CommissionTrans table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>CommissionTrans</p></td>
</tr>
<tr class="even">
<td><p>Shadow_CommissionTrans</p></td>
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
<th><p>From Table: CommissionTrans</p></th>
<th><p>To Table: Shadow_CommissionTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
<tr class="even">
<td><p>EmplId</p></td>
<td><p>Person</p></td>
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
<td><p>CommissionTrans</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
<tr class="even">
<td><p>CommissionTrans</p></td>
<td><p>Person</p></td>
<td><p>CommissionPerson</p></td>
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
<td><p>CommissionTrans</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="even">
<td><p>CommissionTrans</p></td>
<td><p>EmplId</p></td>
</tr>
</tbody>
</table>

  


