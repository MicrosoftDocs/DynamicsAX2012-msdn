---
title: ReleaseUpdateDB41_Basic.updateEmplTable Upgrade Script
TOCTitle: ReleaseUpdateDB41_Basic.updateEmplTable Upgrade Script
ms:assetid: f44d4890-ea4b-5732-27ad-874e911ad25f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737504(v=AX.60)
ms:contentKeyID: 49712198
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Basic.updateEmplTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEmplTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the code for the Basic HRP Employee Party entry.</p></td>
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
<td><p>HRMPartyEmployeeRelationship</p></td>
</tr>
</tbody>
</table>


## Remarks

For each HRP Employee record, we will create an entry in the DirPartyTable table. It also updates HRP Employee table by setting PartyIds to the newly created Party entries. This script assumes that the Party Number Sequence is already set up. This has to be the first upgrade method to be called in the series of HRP Employee Party data upgrades.

  


