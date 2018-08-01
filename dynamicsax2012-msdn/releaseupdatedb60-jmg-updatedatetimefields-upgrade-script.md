---
title: ReleaseUpdateDB60_Jmg.updateDateTimeFields Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.updateDateTimeFields Upgrade Script
ms:assetid: b2290aad-148a-de61-fb9f-31d906f70ecf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736905(v=AX.60)
ms:contentKeyID: 49710589
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.updateDateTimeFields Upgrade Script [AX 2012]


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
<td><p>updateDateTimeFields</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades date and time fields in five Jmg tables to DateTime fields.</p></td>
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
<td><p>DEL_SysUpgradeTimeZone</p></td>
</tr>
<tr class="even">
<td><p>SysInfolog</p></td>
</tr>
<tr class="odd">
<td><p>JmgTimecardTrans</p></td>
</tr>
<tr class="even">
<td><p>JmgTermRegArchive</p></td>
</tr>
<tr class="odd">
<td><p>JmgGroupSigningTable</p></td>
</tr>
<tr class="even">
<td><p>JmgBulletinBoard</p></td>
</tr>
<tr class="odd">
<td><p>JmgAbsenceCalendar</p></td>
</tr>
</tbody>
</table>


## Remarks

Date and time fields are combined to a DateTime value for five Jmg tables.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

