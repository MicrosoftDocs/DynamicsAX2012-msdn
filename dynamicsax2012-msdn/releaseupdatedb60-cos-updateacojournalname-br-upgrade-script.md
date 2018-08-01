---
title: ReleaseUpdateDB60_COS.updateACOJournalName_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_COS.updateACOJournalName_BR Upgrade Script
ms:assetid: 3852dfa0-06bf-0788-3873-9f862424c85e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685206(v=AX.60)
ms:contentKeyID: 49707649
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_COS.updateACOJournalName\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_COS</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateACOJournalName_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts number sequence code to the NumberSequenceTable surrogate key in the ACOJournalName_BR table.</p></td>
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
<td><p>Cost accounting</p></td>
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
<td><p>ACOJournalName_BR</p></td>
</tr>
<tr class="even">
<td><p>NumberSequenceTable</p></td>
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
<td><p>ACOJournalName_BR</p></td>
<td><p>NumberSequenceTable</p></td>
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
<td><p>ACOJournalName_BR</p></td>
<td><p>VoucherSeqId</p></td>
</tr>
</tbody>
</table>

  


