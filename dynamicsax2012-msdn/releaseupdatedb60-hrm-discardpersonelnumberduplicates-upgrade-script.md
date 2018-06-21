---
title: ReleaseUpdateDB60_HRM.discardPersonelNumberDuplicates Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.discardPersonelNumberDuplicates Upgrade Script
ms:assetid: b49e3888-ebf8-606f-a48b-b450fd6a56bb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736979(v=AX.60)
ms:contentKeyID: 49710663
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.discardPersonelNumberDuplicates Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>discardPersonelNumberDuplicates</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Discards the duplicate values of the PersonnelNumber field in the HcmWorker table. Keeps the unique value of the PersonnelNumber field and attaches the value of the dataAreaId field in the DEL_EmplTable table to each duplicate.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>HcmWorker</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade attaches the value of the dataAreaId field of the DEL\_EmplTable to duplicate value of the PersonnelNumber field in the HcmWorker table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

