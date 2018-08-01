---
title: ReleaseUpdateTransformDB50_Lean.initNumberSequences Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Lean.initNumberSequences Upgrade Script
ms:assetid: 88bdcc9c-c6a5-611a-a229-28c9c9023fe8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736374(v=AX.60)
ms:contentKeyID: 49709564
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Lean.initNumberSequences Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Lean</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initNumberSequences</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the number sequences for the KanbanRule card identifiers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Pre-processing60: Single user</p></td>
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
<td><p>Basic</p></td>
</tr>
<tr class="even">
<td><p>Manufacture</p></td>
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
<td><p>KanbanRule</p></td>
</tr>
<tr class="even">
<td><p>NumberSequenceTable</p></td>
</tr>
<tr class="odd">
<td><p>NumberSequenceReference</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: KanbanRule</p></th>
<th><p>To Table: KanbanRule</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CardsNumberSequenceId</p></td>
<td><p>CardsNumberSequenceId</p></td>
</tr>
</tbody>
</table>

  


