---
title: ReleaseUpdateTransformDB50_User.processUserUpgradeDuplicate Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_User.processUserUpgradeDuplicate Upgrade Script
ms:assetid: 2fc4015c-0799-9b97-d120-cb8caf0d201d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736043(v=AX.60)
ms:contentKeyID: 49707458
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_User.processUserUpgradeDuplicate Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_User</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>processUserUpgradeDuplicate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates records into a DEL_UserRelationsContactUpgrade record. The DEL_UserRelationsContactUpgrade table contains duplicates of user relations setup that must be resolved before the upgrade to Microsoft Dynamics AX 2012.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Presync60</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>SysCompanyUserInfo</p></td>
</tr>
<tr class="even">
<td><p>DEL_UserRelationsDuplicateUpgrade</p></td>
</tr>
</tbody>
</table>

  


