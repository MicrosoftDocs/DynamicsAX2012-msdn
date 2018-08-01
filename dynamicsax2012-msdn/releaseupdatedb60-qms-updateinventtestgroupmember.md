---
title: ReleaseUpdateDB60_QMS.updateInventTestGroupMember
TOCTitle: ReleaseUpdateDB60_QMS.updateInventTestGroupMember
ms:assetid: 9216a5d0-050e-4316-3cea-72c04c0e2227
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736598(v=AX.60)
ms:contentKeyID: 49709786
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_QMS.updateInventTestGroupMember 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_QMS</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateInventTestGroupMember</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the QmmTestGroupMember table to the InventTestGroupMember table.</p></td>
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
<td><p>Quality Management System</p></td>
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
<td><p>DEL_QmmTestGroupMember</p></td>
</tr>
<tr class="even">
<td><p>InventTestGroupMember</p></td>
</tr>
</tbody>
</table>


## Remarks

This script is set to be dependent on the ReleaseUpdateDB60\_Basic.updateUnitOfMeasureConsumers upgrade script that updates units of measure in all application tables. By doing this we ensure that mentioned script will be executed on the empty InventTestGroupMember table. Units of measure for the InventTestGroupMember table will be updated afterwards by the ReleaseUpdateDB60\_QMS.updateUnitOfMeasureQMSConsumers upgrade script.

  


