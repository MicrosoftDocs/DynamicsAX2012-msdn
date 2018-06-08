---
title: ReleaseUpdateDB60_PBA.allowNoDupPBATreeSimpelPBANodeIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_PBA.allowNoDupPBATreeSimpelPBANodeIdx Upgrade Script
ms:assetid: 794559b6-a407-8230-07b8-d5c0c6dcc43d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719401(v=AX.60)
ms:contentKeyID: 49709192
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PBA.allowNoDupPBATreeSimpelPBANodeIdx Upgrade Script 


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
<td><p>allowNoDupPBATreeSimpelPBANodeIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Restores the unique PBANodeIdx index of the PBATreeSimpel table.</p></td>
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
<td><p>SqlDictionary</p></td>
</tr>
<tr class="even">
<td><p>SysConfig</p></td>
</tr>
<tr class="odd">
<td><p>SysInfolog</p></td>
</tr>
<tr class="even">
<td><p>SysSetupLog</p></td>
</tr>
</tbody>
</table>


## Remarks

As the PBANodeIdx index changed fields between Microsoft Dynamics AX 2009 and Microsoft Dynamics AX 2012, the upgrade process requires the index to be marked as non-unique during the upgrade and then restored afterwards.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

