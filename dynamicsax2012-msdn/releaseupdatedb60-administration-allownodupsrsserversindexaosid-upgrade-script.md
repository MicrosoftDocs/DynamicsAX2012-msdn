---
title: ReleaseUpdateDB60_Administration.allowNoDupSRSServersIndexAOSId Upgrade Script
TOCTitle: ReleaseUpdateDB60_Administration.allowNoDupSRSServersIndexAOSId Upgrade Script
ms:assetid: 09ca4655-33a3-eadf-fb20-be2b097d46be
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735600(v=AX.60)
ms:contentKeyID: 49706510
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Administration.allowNoDupSRSServersIndexAOSId Upgrade Script [AX 2012]


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
<td><p>allowNoDupSRSServersIndexAOSId</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Disables the allow duplicates property for the new unique AOSId index.</p></td>
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
<td><p>Administration</p></td>
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
<td><p>SSRSServers</p></td>
</tr>
</tbody>
</table>


## Remarks

Sets back the AOSID index to the original state to not allow duplicate records with the same value for the AOSId field.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

