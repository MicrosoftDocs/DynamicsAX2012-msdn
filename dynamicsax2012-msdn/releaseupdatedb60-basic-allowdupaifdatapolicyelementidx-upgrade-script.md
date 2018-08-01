---
title: ReleaseUpdateDB60_Basic.allowDupAifDataPolicyElementIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupAifDataPolicyElementIdx Upgrade Script
ms:assetid: 7e23c36c-1794-968e-ef46-dc6686f856b6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685846(v=AX.60)
ms:contentKeyID: 49709300
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupAifDataPolicyElementIdx Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>allowDupAifDataPolicyElementIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a table mapping between the AifDataPolicy and DEL_AifDataPolicy50 tables.</p></td>
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
<td><p>AifDataPolicy</p></td>
</tr>
<tr class="even">
<td><p>DEL_AifDataPolicy50</p></td>
</tr>
</tbody>
</table>


## Remarks

The data policy records in the AifDataPolicy table are copied to the DEL\_AIFDataPolicy50 table. This method is to be run as a PreSync Shared Job.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AifDataPolicy</p></th>
<th><p>To Table: DEL_AifDataPolicy50</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

