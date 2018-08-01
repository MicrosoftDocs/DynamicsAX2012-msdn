---
title: ReleaseUpdateDB60_Basic.allowNoDupEFDReturnCode_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowNoDupEFDReturnCode_BR Upgrade Script
ms:assetid: a493be68-dacd-02d8-19e4-c11fd31b55a3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736817(v=AX.60)
ms:contentKeyID: 49710248
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowNoDupEFDReturnCode\_BR Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupEFDReturnCode_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Re-enables message type index in the EFDReturnCode_BR code after the data has migrated from company to enterprise level.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>EFDReturnCode_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

The index is disabled by the allowDupEFDReturnCode\_BR code and re-enabled by the allowNoDupEFDReturnCode\_BR code in post-sync stage after data in the EFDReturnCode\_BR code has been properly set.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

