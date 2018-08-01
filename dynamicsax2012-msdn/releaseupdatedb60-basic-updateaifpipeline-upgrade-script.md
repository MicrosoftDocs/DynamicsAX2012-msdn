---
title: ReleaseUpdateDB60_Basic.updateAifPipeline Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateAifPipeline Upgrade Script
ms:assetid: db42ec0b-811e-1ff9-e8fe-1baf87c5fad3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737165(v=AX.60)
ms:contentKeyID: 49711608
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateAifPipeline Upgrade Script 


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
<td><p>updateAifPipeline</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records in the AifPipeline table from the DEL_AifPipeline50 table.</p></td>
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
<td><p>AifPort</p></td>
</tr>
<tr class="even">
<td><p>AifInboundPort</p></td>
</tr>
<tr class="odd">
<td><p>AifPortActionPolicy</p></td>
</tr>
<tr class="even">
<td><p>AifPipeline</p></td>
</tr>
<tr class="odd">
<td><p>AifEndpoint</p></td>
</tr>
<tr class="even">
<td><p>DEL_AifPipeline50</p></td>
</tr>
<tr class="odd">
<td><p>DEL_AifUpgradeEndpointPortMap</p></td>
</tr>
</tbody>
</table>


## Remarks

This method should be run as an additional shared script.

  


