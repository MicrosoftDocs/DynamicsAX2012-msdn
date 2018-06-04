---
title: ReleaseUpdateDB60_Req.createReqPlanLock
TOCTitle: ReleaseUpdateDB60_Req.createReqPlanLock
ms:assetid: add91c4c-66a6-d299-c22c-e920c144ac89
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686529(v=AX.60)
ms:contentKeyID: 49710484
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Req.createReqPlanLock 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Req</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createReqPlanLock</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the default records in the &lt;c&gt;ReqPlanLock&lt;/c&gt; table.</p></td>
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
<td><p>Master planning</p></td>
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
<td><p>ReqPlanLock</p></td>
</tr>
</tbody>
</table>


## Remarks

For each master plan, the record is inserted into the \<c\>ReqPlanLock\</c\> table with the value of the \<c\>IsLocked\</c\> field set to zero.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

