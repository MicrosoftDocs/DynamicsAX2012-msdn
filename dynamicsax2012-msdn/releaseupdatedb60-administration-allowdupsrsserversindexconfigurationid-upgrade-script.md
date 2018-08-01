---
title: ReleaseUpdateDB60_Administration.allowDupSRSServersIndexConfigurationId Upgrade Script
TOCTitle: ReleaseUpdateDB60_Administration.allowDupSRSServersIndexConfigurationId Upgrade Script
ms:assetid: 5ad2e58b-ff3d-fce0-0663-b9787e8b169c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736297(v=AX.60)
ms:contentKeyID: 49708468
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Administration.allowDupSRSServersIndexConfigurationId Upgrade Script 


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
<td><p>allowDupSRSServersIndexConfigurationId</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Enables the allow duplicates property for the new unique ConfigurationId index.</p></td>
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

Temporarily sets the ConfigurationID index to allow records with the same value for the ConfigurationID field during the upgrade.

  


