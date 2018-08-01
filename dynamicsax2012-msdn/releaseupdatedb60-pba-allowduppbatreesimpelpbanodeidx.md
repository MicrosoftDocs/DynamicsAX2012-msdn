---
title: ReleaseUpdateDB60_PBA.allowDupPBATreeSimpelPBANodeIdx
TOCTitle: ReleaseUpdateDB60_PBA.allowDupPBATreeSimpelPBANodeIdx
ms:assetid: d1628260-aa20-a94d-6f4b-54444620d0a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686930(v=AX.60)
ms:contentKeyID: 49711380
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PBA.allowDupPBATreeSimpelPBANodeIdx [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>Allows duplicate records to occur during the upgrade process over the unique &lt;c&gt;PBANodeIdx&lt;/c&gt; index of the &lt;c&gt;PBATreeSimpel&lt;/c&gt; table.</p></td>
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

As the \<c\>PBANodeIdx\</c\> index changed fields between AX 5.0 and 6.0, the upgrade process requires the index to be marked as non-unique during the upgrade and restored afterwards.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

