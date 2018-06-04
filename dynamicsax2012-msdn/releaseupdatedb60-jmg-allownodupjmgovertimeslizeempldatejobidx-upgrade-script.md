---
title: ReleaseUpdateDB60_Jmg.allowNoDupJmgOvertimeSlizeEmplDateJobIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.allowNoDupJmgOvertimeSlizeEmplDateJobIdx Upgrade Script
ms:assetid: 758922ab-adbb-c480-1e5c-10fbcc3cc172
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719319(v=AX.60)
ms:contentKeyID: 49709111
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.allowNoDupJmgOvertimeSlizeEmplDateJobIdx Upgrade Script 


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
<td><p>allowNoDupJmgOvertimeSlizeEmplDateJobIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EmplDateJobIdx index in the JmgOvertimeSlize table not to allow for duplicate records.</p></td>
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
<td><p>JmgOvertimeSlize</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the Worker surrogate key field with the value of the RecId field of the HcmWorker table, the EmplDateJobIdx index is reset not to allow for 2duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

