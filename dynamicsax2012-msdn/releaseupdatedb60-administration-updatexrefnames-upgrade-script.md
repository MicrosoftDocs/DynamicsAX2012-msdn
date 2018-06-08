---
title: ReleaseUpdateDB60_Administration.updatexRefNames Upgrade Script
TOCTitle: ReleaseUpdateDB60_Administration.updatexRefNames Upgrade Script
ms:assetid: 4d4d4ea0-5b3f-176a-d4c0-f3634e93aa75
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685428(v=AX.60)
ms:contentKeyID: 49708134
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Administration.updatexRefNames Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Administration</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatexRefNames</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The xRefNames table contains the AOT node names in the cross reference is not required to be copied over, since the cross reference information has to be fully regenerated as part of the upgrade process.</p></td>
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
<td><p>xRefNames</p></td>
</tr>
</tbody>
</table>


## Remarks

The updatexRefNames method in the class ReleaseUpdateDB60\_Administration skips copying during the upgrade process the information in the xRefNames table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

