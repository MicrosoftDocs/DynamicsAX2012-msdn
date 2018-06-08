---
title: ReleaseUpdateDB60_Basic.updateOperatingUnit Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateOperatingUnit Upgrade Script
ms:assetid: 3668d02c-1e0c-aca9-2a5a-3f908bdec353
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685169(v=AX.60)
ms:contentKeyID: 49707622
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateOperatingUnit Upgrade Script 


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
<td><p>updateOperatingUnit</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the OMOperatingUnitNumber field in the OMOperatingUnit table so that it has valid and unique values for all records.</p></td>
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
<td><p>OMOperatinUnit</p></td>
</tr>
</tbody>
</table>


## Remarks

This step is performed before allowDupOMOperatingUnit is called to ensure that calling the allowDupOMOperatingUnit routine will not cause an index violation because the OMOperatingUnitNumber field had invalid/duplicate values.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

