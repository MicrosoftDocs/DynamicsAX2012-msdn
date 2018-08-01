---
title: ReleaseUpdateDB60_Basic.allowDupAifPipelineMessageDirectionIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupAifPipelineMessageDirectionIdx Upgrade Script
ms:assetid: 291c204f-668c-c602-7567-918674286c8c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735885(v=AX.60)
ms:contentKeyID: 49707303
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupAifPipelineMessageDirectionIdx Upgrade Script 


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
<td><p>allowDupAifPipelineMessageDirectionIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a table mapping between the AifPipeline and DEL_AifPipeline50 tables.</p></td>
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
<td><p>AifPipeline</p></td>
</tr>
<tr class="even">
<td><p>DEL_AifPipeline50</p></td>
</tr>
</tbody>
</table>


## Remarks

Pipelines in AifPipeline table are copied to the DEL\_AifPipeline50 table. This method is to be run as a PreSync Shared Job.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AifPipeline</p></th>
<th><p>To Table: DEL_AifPipeline50</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


