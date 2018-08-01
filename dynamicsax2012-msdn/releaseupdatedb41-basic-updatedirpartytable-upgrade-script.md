---
title: ReleaseUpdateDB41_Basic.updateDirPartyTable Upgrade Script
TOCTitle: ReleaseUpdateDB41_Basic.updateDirPartyTable Upgrade Script
ms:assetid: 2255b97e-7185-b1f8-4d90-c4b1c13a41bc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684946(v=AX.60)
ms:contentKeyID: 49707147
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Basic.updateDirPartyTable Upgrade Script 


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
<td><p>updateDirPartyTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the business relation and contact person entries.</p></td>
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
<td><p>CustTable</p></td>
</tr>
<tr class="even">
<td><p>DEL_upgradeBusRelTable</p></td>
</tr>
<tr class="odd">
<td><p>VendTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Creates an entry in the dirPartyTable table and logs the mapping into the upgradeBusRel\_PartyTable and upgradeContact\_PartyTable tables, respectively. It also updates BR and the ContactPerson table by setting the party IDs to the newly created party entries. It also creates entries in the dirPartytable table for competitors who do not have corresponding business relation entries.

  


