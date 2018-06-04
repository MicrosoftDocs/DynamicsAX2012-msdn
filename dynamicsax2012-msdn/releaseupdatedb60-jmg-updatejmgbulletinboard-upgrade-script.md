---
title: ReleaseUpdateDB60_Jmg.updateJmgBulletinBoard Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.updateJmgBulletinBoard Upgrade Script
ms:assetid: 1f6917df-553c-5414-54f5-6b0387248292
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684866(v=AX.60)
ms:contentKeyID: 49707067
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.updateJmgBulletinBoard Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Jmg</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateJmgBulletinBoard</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the JmgBulletinBoard table to support the new message system for the registration client.</p></td>
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
<td><p>Shop Floor Control</p></td>
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
<td><p>JmgBulletinBoard</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the view date and time to a combined DateTime value.

## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JmgBulletinBoard</p></td>
<td><p>ViewDateTime</p></td>
<td><p>JmgDateTime</p></td>
</tr>
<tr class="even">
<td><p>JmgBulletinBoard</p></td>
<td><p>ViewDateTimeTo</p></td>
<td><p>JmgDateTime</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>JmgBulletinBoard</p></td>
<td><p>ViewDate</p></td>
</tr>
<tr class="even">
<td><p>JmgBulletinBoard</p></td>
<td><p>ViewTime</p></td>
</tr>
<tr class="odd">
<td><p>JmgBulletinBoard</p></td>
<td><p>ViewDateTo</p></td>
</tr>
<tr class="even">
<td><p>JmgBulletinBoard</p></td>
<td><p>ViewTimeTo</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

