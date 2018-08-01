---
title: ReleaseUpdateDB60_Administration.updateSysUtilElementsLog Upgrade Script
TOCTitle: ReleaseUpdateDB60_Administration.updateSysUtilElementsLog Upgrade Script
ms:assetid: f9c3deff-3f10-a9aa-df13-706e441258da
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720047(v=AX.60)
ms:contentKeyID: 49712353
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Administration.updateSysUtilElementsLog Upgrade Script 


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
<td><p>updateSysUtilElementsLog</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Truncates the data in the SysUtilElementsLog table.</p></td>
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
<td><p>SysUtilElementsLog</p></td>
</tr>
</tbody>
</table>


## Remarks

The update frequency of the ElementUsageLog is changed from once per element per user per 15 minutes to once per day for all users. Data collected with the former frequency is incompatible with the new data, and it is being truncated.

  


