---
title: ReleaseUpdateDB60_Basic.updateAifGatewayQueue Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateAifGatewayQueue Upgrade Script
ms:assetid: 4e5241ec-eec5-e5e2-9673-c19a4d3121d1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685463(v=AX.60)
ms:contentKeyID: 49708168
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateAifGatewayQueue Upgrade Script 


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
<td><p>updateAifGatewayQueue</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a field mapping in the AifGatewayQueue table between the RequestMesageId and OriginalMessageId fields.</p></td>
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
<td><p>AifGatewayQueue</p></td>
</tr>
</tbody>
</table>


## Remarks

This table should be empty before the upgrade. This method should be run as a PreSync shared script.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

