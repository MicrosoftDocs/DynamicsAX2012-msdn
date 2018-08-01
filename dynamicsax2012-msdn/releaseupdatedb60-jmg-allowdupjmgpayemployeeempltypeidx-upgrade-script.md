---
title: ReleaseUpdateDB60_Jmg.allowDupJmgPayEmployeeEmplTypeIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.allowDupJmgPayEmployeeEmplTypeIdx Upgrade Script
ms:assetid: 1157bf2a-38d9-264f-fc9f-4dc8b71a321a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735800(v=AX.60)
ms:contentKeyID: 49706710
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.allowDupJmgPayEmployeeEmplTypeIdx Upgrade Script 


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
<td><p>allowDupJmgPayEmployeeEmplTypeIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EmplTypeIdx index in the JmgPayEmployee table to allow for duplicate records.</p></td>
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
<td><p>JmgPayEmployee</p></td>
</tr>
</tbody>
</table>


## Remarks

The EmplId field is replaced with the new Worker surrogate key field, and the Worker field replaces the EmplId field in the unique EmplTypeIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the HcmWorker table.

  


