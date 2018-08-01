---
title: ReleaseUpdateDB60_Basic.upgradeNumberSequenceTables Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.upgradeNumberSequenceTables Upgrade Script
ms:assetid: f23e1910-7b26-3ed7-3c45-ee8f460f302e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737452(v=AX.60)
ms:contentKeyID: 49712146
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.upgradeNumberSequenceTables Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>upgradeNumberSequenceTables</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Removes the formatting from the NumberSequenceList table. For each extended data type that is found that references the number sequence table gets a number sequence record, for a default scope, created for it if none exists.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>NumberSequenceTable</p></td>
</tr>
<tr class="even">
<td><p>NumberSequenceList</p></td>
</tr>
<tr class="odd">
<td><p>NumberSequenceReference</p></td>
</tr>
</tbody>
</table>


## Remarks

Copies other tables, like the numbersequencehistory table and the numbersequencegroup table.

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
<td><p>NumberSequenceList</p></td>
<td><p>nextrec</p></td>
<td><p>numberseqencerange</p></td>
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
<td><p>NumberSequenceList</p></td>
<td><p>Num</p></td>
</tr>
</tbody>
</table>

  


