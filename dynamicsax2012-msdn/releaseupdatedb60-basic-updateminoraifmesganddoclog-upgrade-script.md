---
title: ReleaseUpdateDB60_Basic.updateMinorAifMesgAndDocLog Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateMinorAifMesgAndDocLog Upgrade Script
ms:assetid: a2bd2529-9c8b-3a81-e26b-003bb4a25b23
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736752(v=AX.60)
ms:contentKeyID: 49710184
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateMinorAifMesgAndDocLog Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateMinorAifMesgAndDocLog</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the current partition on the AifMessageLog and the AifDocumentLog table records.</p></td>
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
<td><p>AifMessageLog</p></td>
</tr>
<tr class="even">
<td><p>AifDocumentLog</p></td>
</tr>
</tbody>
</table>


## Remarks

This script is used for a minor version upgrade. In this case, all companies are mapped to a single partition. This script sets the new partition for the records in the AifMessageLog and AifDocumentLog tables.

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
<td><p>AifMessageLog</p></td>
<td><p>DataPartition</p></td>
<td><p>Partition</p></td>
</tr>
<tr class="even">
<td><p>AifDocumentLog</p></td>
<td><p>DataPartition</p></td>
<td><p>Partition</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

