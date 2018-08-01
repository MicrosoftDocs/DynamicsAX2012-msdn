---
title: ReleaseUpdateTransformDB50_User.validateUserUpgradeDuplicate Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_User.validateUserUpgradeDuplicate Upgrade Script
ms:assetid: 42cf631e-2080-a657-7422-a7657b5c228f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718853(v=AX.60)
ms:contentKeyID: 49707897
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_User.validateUserUpgradeDuplicate Upgrade Script [AX 2012]


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
<td><p>validateUserUpgradeDuplicate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates the upgrade check set on a DEL_UserRelationsContactUpgrade record.</p></td>
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
<tr class="odd">
<td><p>DEL_UserRelationsUpgradeHelper</p></td>
</tr>
</tbody>
</table>


## Remarks

For each user ID, there should be exactly one record with the upgrade set to Yes.

Re-running the populating script is a part of validation, since cross company duplicates of user relations setup must be resolved before the upgrade to Microsoft Dynamics AX 2012. This script searches all companies.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

