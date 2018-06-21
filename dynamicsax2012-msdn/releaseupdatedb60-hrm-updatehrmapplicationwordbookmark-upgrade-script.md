---
title: ReleaseUpdateDB60_HRM.updateHRMApplicationWordBookmark Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMApplicationWordBookmark Upgrade Script
ms:assetid: 3d55d864-4b29-c2a4-ebc1-851a4fb96313
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718739(v=AX.60)
ms:contentKeyID: 49707784
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMApplicationWordBookmark Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHRMApplicationWordBookmark</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the HRMApplicationWordBookmak table to replace all FieldId values in the Bookmark field with the associated FieldName value.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>HRMApplicationWordBookmark</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to comply with the removal of FieldId values from Container data types.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

