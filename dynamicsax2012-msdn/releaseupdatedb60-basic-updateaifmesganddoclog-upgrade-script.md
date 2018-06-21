---
title: ReleaseUpdateDB60_Basic.updateAifMesgAndDocLog Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateAifMesgAndDocLog Upgrade Script
ms:assetid: e08e285a-91e6-7362-4b01-34fe69e6f087
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737272(v=AX.60)
ms:contentKeyID: 49711714
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateAifMesgAndDocLog Upgrade Script [AX 2012]


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
<td><p>updateAifMesgAndDocLog</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the AifMessageLog table and the AifDocumentLog table from the DEL_AifMessageLog table and the DEL_AifDocumentLog respectively.</p></td>
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

The AifMessageLog table and the AifDocumentLog table have changed from being company specific to being global across companies and partitions. This script will also add the new partition information to the DataPartition field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AifMessageLog</p></th>
<th><p>To Table: AifMessageLog</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>Company</p></td>
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
<td><p>AifMessageLog</p></td>
<td><p>DataAreaId</p></td>
</tr>
<tr class="even">
<td><p>AifDocumentLog</p></td>
<td><p>DataAreaId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

