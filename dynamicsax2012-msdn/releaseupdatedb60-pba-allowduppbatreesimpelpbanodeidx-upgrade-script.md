---
title: ReleaseUpdateDB60_PBA.allowDupPBATreeSimpelPBANodeIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_PBA.allowDupPBATreeSimpelPBANodeIdx Upgrade Script
ms:assetid: d3cf0961-e2b6-001a-aced-1154bece9900
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686981(v=AX.60)
ms:contentKeyID: 49711432
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PBA.allowDupPBATreeSimpelPBANodeIdx Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_PBA</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupPBATreeSimpelPBANodeIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Allows duplicate records to occur during the upgrade process over the unique PBANodeIdx index of the PBATreeSimpel table.</p></td>
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
<td><p>Product Builder</p></td>
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
<td><p>SysInfolog</p></td>
</tr>
</tbody>
</table>


## Remarks

As the PBANodeIdx index changed fields between Microsoft Dynamics AX 2009 and Microsoft Dynamics AX 2012, the upgrade process requires the index to be marked as non-unique during the upgrade and then restored afterwards.

  


