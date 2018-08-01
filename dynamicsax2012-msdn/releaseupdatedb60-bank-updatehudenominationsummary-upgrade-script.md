---
title: ReleaseUpdateDB60_Bank.updateHUDenominationSummary Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.updateHUDenominationSummary Upgrade Script
ms:assetid: 97fc33d0-2c50-85ea-5d93-8a225263c449
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686227(v=AX.60)
ms:contentKeyID: 49709930
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.updateHUDenominationSummary Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Bank</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHUDenominationSummary</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the HuDenominations field of the HuDenominationSummary table with the RecId field of the HuDenominationSummary table.</p></td>
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
<td><p>Bank</p></td>
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
<td><p>HuDenominationSummary</p></td>
</tr>
</tbody>
</table>


## Remarks

A new surrogate foreign key relation has been created to the HuDenominations table and the HuDenominationSummary table now stores that reference instead of storing the Name value.

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
<td><p>HuDenominationSummary</p></td>
<td><p>HuDenominations</p></td>
<td><p>RefRecId</p></td>
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
<td><p>HuDenominationSummary</p></td>
<td><p>DEL_Name</p></td>
</tr>
</tbody>
</table>

  


