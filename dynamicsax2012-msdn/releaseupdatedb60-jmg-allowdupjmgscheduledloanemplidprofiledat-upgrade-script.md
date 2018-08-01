---
title: ReleaseUpdateDB60_Jmg.allowDupJmgScheduledLoanEmplIdProfileDat Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.allowDupJmgScheduledLoanEmplIdProfileDat Upgrade Script
ms:assetid: 9fe95c58-f32d-a7f3-572f-f52b2062e5a2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736688(v=AX.60)
ms:contentKeyID: 49710120
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.allowDupJmgScheduledLoanEmplIdProfileDat Upgrade Script [AX 2012]


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
<td><p>allowDupJmgScheduledLoanEmplIdProfileDat</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EmplIdProfileDateIdx index in the JmgScheduledLoan table to allow for duplicate records.</p></td>
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
<td><p>JmgScheduledLoan</p></td>
</tr>
</tbody>
</table>


## Remarks

The EmplId field is replaced with the new Worker surrogate key field, and the Worker field replaces the EmplId field in the unique EmplIdProfileDateIdx index. Initially this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the HcmWorker table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

