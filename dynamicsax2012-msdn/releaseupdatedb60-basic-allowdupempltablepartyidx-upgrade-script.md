---
title: ReleaseUpdateDB60_Basic.allowDupEmplTablePartyIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.allowDupEmplTablePartyIdx Upgrade Script
ms:assetid: 7561c4f3-3a65-3805-1aad-db3af44cbb8d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719298(v=AX.60)
ms:contentKeyID: 49709089
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.allowDupEmplTablePartyIdx Upgrade Script 


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
<td><p>allowDupEmplTablePartyIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Party index in the table EmplTable table to allow duplicate records.</p></td>
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
<td><p>EmplTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The index is set to allow duplicates for the party which is a new field as of Microsoft Dynamics AX 2012 in the EmplTable table.

  


