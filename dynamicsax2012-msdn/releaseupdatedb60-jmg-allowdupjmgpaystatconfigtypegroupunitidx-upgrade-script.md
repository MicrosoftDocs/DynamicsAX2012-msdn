---
title: ReleaseUpdateDB60_Jmg.allowDupJmgPayStatConfigTypeGroupUnitIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.allowDupJmgPayStatConfigTypeGroupUnitIdx Upgrade Script
ms:assetid: 33163b90-1ff4-9007-6e4c-93a7fe9d5294
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685092(v=AX.60)
ms:contentKeyID: 49707546
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.allowDupJmgPayStatConfigTypeGroupUnitIdx Upgrade Script [AX 2012]


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
<td><p>allowDupJmgPayStatConfigTypeGroupUnitIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TypeGroupUnitIdx index in the JmgPayStatConfig table to allow for duplicate records.</p></td>
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
<td><p>JmgPayStatConfig</p></td>
</tr>
</tbody>
</table>


## Remarks

The PayrollPeriod field is replaced with the new ProjPeriodId field in the unique TypeGroupUnitIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

