---
title: ReleaseUpdateDB60_Basic.udpateNumberSequenceFrameworkPostSync Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.udpateNumberSequenceFrameworkPostSync Upgrade Script
ms:assetid: 574e7234-77ee-3f37-250f-9528202c3a5a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736204(v=AX.60)
ms:contentKeyID: 49708379
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.udpateNumberSequenceFrameworkPostSync Upgrade Script [AX 2012]


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
<td><p>udpateNumberSequenceFrameworkPostSync</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts and populates the number sequence framework tables.</p></td>
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
<td><p>numbersequencedatatypes</p></td>
</tr>
<tr class="even">
<td><p>numbersequencedataypeparametertypes</p></td>
</tr>
<tr class="odd">
<td><p>numbersequencetable</p></td>
</tr>
<tr class="even">
<td><p>numbersequencegroup</p></td>
</tr>
<tr class="odd">
<td><p>NumbersequenceGroupRef</p></td>
</tr>
<tr class="even">
<td><p>NumberSequenceReference</p></td>
</tr>
<tr class="odd">
<td><p>NumberSequenceReference</p></td>
</tr>
<tr class="even">
<td><p>Numbersequencehistory</p></td>
</tr>
<tr class="odd">
<td><p>NumberSequenceLsit</p></td>
</tr>
<tr class="even">
<td><p>NumbersequenceList</p></td>
</tr>
<tr class="odd">
<td><p>NumbersequenceTTs</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
</tr>
</tbody>
</table>


## Remarks

Copies the framework number sequence tables and removes formatting from them. Creates number sequences for each module EDT and provides a default scope.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

