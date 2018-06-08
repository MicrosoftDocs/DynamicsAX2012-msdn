---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximDEPBScheduleTable_INProduc
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximDEPBScheduleTable_INProduc
ms:assetid: b2e13b1b-6fcb-d3d4-72b3-bd32a0d7e51e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736915(v=AX.60)
ms:contentKeyID: 49710599
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximDEPBScheduleTable\_INProduc 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupEximDEPBScheduleTable_INProduc</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;ProductGroupTableRecIdx&lt;/c&gt; in the table &lt;c&gt;EximDEPBScheduleTable_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>EXIMDEPBSCHEDULETABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

Previous nonunique index is now unique. Upgrade script required.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

