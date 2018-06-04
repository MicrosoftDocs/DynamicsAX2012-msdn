---
title: ReleaseUpdateTransformDB50_GAB.ProjTable Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_GAB.ProjTable Upgrade Script
ms:assetid: f4bab12d-ed45-ad61-38d6-779d06ffb3eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737558(v=AX.60)
ms:contentKeyID: 49712251
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_GAB.ProjTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_GAB</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ProjTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the address related data in the ProjTable with the new Global Address Book data model.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>CRM</p></td>
</tr>
<tr class="even">
<td><p>Project</p></td>
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
<td><p>LogisticsPostalAddress</p></td>
</tr>
<tr class="even">
<td><p>ProjTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The script creates new LogisticsPostalAddress records and assigns the appropriate references to the ProjTable table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

