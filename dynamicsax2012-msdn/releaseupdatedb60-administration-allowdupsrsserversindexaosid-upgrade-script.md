---
title: ReleaseUpdateDB60_Administration.allowDupSRSServersIndexAOSId Upgrade Script
TOCTitle: ReleaseUpdateDB60_Administration.allowDupSRSServersIndexAOSId Upgrade Script
ms:assetid: 578fe1c4-5cbb-07e0-e328-27e0ab1f7deb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736214(v=AX.60)
ms:contentKeyID: 49708389
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Administration.allowDupSRSServersIndexAOSId Upgrade Script 


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
<td><p>allowDupSRSServersIndexAOSId</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Enables the allow duplicates property for the new unique AOSId index.</p></td>
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
<td><p>SRSServers</p></td>
</tr>
</tbody>
</table>


## Remarks

Temporarily sets the AOSID index to allow records with the same value for the AOSId field during the upgrade.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

