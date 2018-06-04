---
title: ReleaseUpdateDB60_Req.updateReqSitePolicy
TOCTitle: ReleaseUpdateDB60_Req.updateReqSitePolicy
ms:assetid: 56018cff-a5d4-c0e9-a5e3-4f66a7c8556e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736194(v=AX.60)
ms:contentKeyID: 49708369
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Req.updateReqSitePolicy 


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
<td><p>updateReqSitePolicy</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the default records in the &lt;c&gt;ReqSitePolicy&lt;/c&gt; table.</p></td>
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
<td><p>ReqSitePolicy</p></td>
</tr>
</tbody>
</table>


## Remarks

For each site, the record is created in the \<c\>ReqSitePolicy\</c\> table with the value of the \<c\>UseTransferJournals\</c\> field set to false.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

