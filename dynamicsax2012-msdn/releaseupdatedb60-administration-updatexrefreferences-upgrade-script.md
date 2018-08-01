---
title: ReleaseUpdateDB60_Administration.updatexRefReferences Upgrade Script
TOCTitle: ReleaseUpdateDB60_Administration.updatexRefReferences Upgrade Script
ms:assetid: cefee560-f83c-1a43-365c-33843bb55ac7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686891(v=AX.60)
ms:contentKeyID: 49711342
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Administration.updatexRefReferences Upgrade Script [AX 2012]


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
<td><p>updatexRefReferences</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The xRefReferences table that contains the references between AOT nodes is not required to be copied over, since the cross reference information has to be fully regenerated as part of the upgrade process.</p></td>
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
<td><p>xRefReferences</p></td>
</tr>
</tbody>
</table>


## Remarks

The updatexRefReferences method in the ReleaseUpdateDB60\_Administration class skips copying the information in the xRefReferences table during the upgrade script process.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

