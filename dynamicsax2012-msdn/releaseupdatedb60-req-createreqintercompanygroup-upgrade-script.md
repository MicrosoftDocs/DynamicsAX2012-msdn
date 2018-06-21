---
title: ReleaseUpdateDB60_Req.createReqIntercompanyGroup Upgrade Script
TOCTitle: ReleaseUpdateDB60_Req.createReqIntercompanyGroup Upgrade Script
ms:assetid: 886cd6ce-9b85-a8d0-7d63-5b3dadbb53fc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736360(v=AX.60)
ms:contentKeyID: 49709550
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Req.createReqIntercompanyGroup Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>createReqIntercompanyGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a new default intercompany planning group which contains as members all companies that have an intercompany plan setup in the master planning parameters.</p></td>
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
<td><p>ReqIntercompanyPlanningGroup</p></td>
</tr>
<tr class="even">
<td><p>ReqIntercompanyPlanningGroupMember</p></td>
</tr>
<tr class="odd">
<td><p>ReqParameters</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

