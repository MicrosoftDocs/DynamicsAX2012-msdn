---
title: ReleaseUpdateDB60_Basic.createAifPort Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.createAifPort Upgrade Script
ms:assetid: 30e365dc-9803-1276-7294-10546f0217c5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736074(v=AX.60)
ms:contentKeyID: 49707488
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.createAifPort Upgrade Script [AX 2012]


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
<td><p>createAifPort</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the AifInboundPort and AifOutboundPort records based on the AifEndpoint records.</p></td>
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
<td><p>AifOutboundPort</p></td>
</tr>
<tr class="even">
<td><p>AifEndpoint</p></td>
</tr>
<tr class="odd">
<td><p>DEL_AifUpgradeEndpointPortMap</p></td>
</tr>
</tbody>
</table>


## Remarks

This script is to be run as an additional shared job.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

