---
title: ReleaseUpdateDB60_Basic.addAifResponseException Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.addAifResponseException Upgrade Script
ms:assetid: a3cffef8-8f52-e503-ee71-9add92519bbb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736767(v=AX.60)
ms:contentKeyID: 49710199
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.addAifResponseException Upgrade Script 


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
<td><p>addAifResponseException</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Adds a bulk copy exception of DoNotCopy to prevent a bulk copy of records from the &lt;c&gt;AifResponse&lt;/c&gt; table.</p></td>
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
<td><p>AifResponse</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>AifResponse\</c\> table is used for correlating responses to requests. Responses cannot be correlated across versions and records from this table should not be copied to the new version.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

