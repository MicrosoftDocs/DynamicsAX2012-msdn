﻿---
title: ReleaseUpdateDB60_Basic.updateDEL_DirECommunicationTypeTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateDEL_DirECommunicationTypeTable Upgrade Script
ms:assetid: b429d013-fbb1-563c-a8aa-4d2ada07034c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736956(v=AX.60)
ms:contentKeyID: 49710640
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateDEL\_DirECommunicationTypeTable Upgrade Script 


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
<td><p>updateDEL_DirECommunicationTypeTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies rows from the DEL_DirECommunicationTypeTable table to the LogisticselectronicAddressType table, and updates references in ShipCarrierEmailAddress table to use the LogisticselectronicAddressType table.</p></td>
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
<td><p>DirECommunicationTypeTable</p></td>
</tr>
<tr class="even">
<td><p>ShipCarrierEmailAddress</p></td>
</tr>
</tbody>
</table>

  


