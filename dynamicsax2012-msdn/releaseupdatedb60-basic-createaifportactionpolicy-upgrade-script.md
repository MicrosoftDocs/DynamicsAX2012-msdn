---
title: ReleaseUpdateDB60_Basic.createAifPortActionPolicy Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.createAifPortActionPolicy Upgrade Script
ms:assetid: 337be4a3-fe8e-f7b0-8a1d-f92d89341891
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685101(v=AX.60)
ms:contentKeyID: 49707555
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.createAifPortActionPolicy Upgrade Script 


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
<td><p>createAifPortActionPolicy</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Moves data from the DEL_AifEndpointActionPolicy table to the AifPortActionPolicy table. This also populates the AifPortDocument table.</p></td>
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
<td><p>AifPort</p></td>
</tr>
<tr class="even">
<td><p>AifPortActionPolicy</p></td>
</tr>
<tr class="odd">
<td><p>AifPortDocument</p></td>
</tr>
<tr class="even">
<td><p>AifEndpoint</p></td>
</tr>
<tr class="odd">
<td><p>AifEndpointActionPolicy</p></td>
</tr>
<tr class="even">
<td><p>DEL_AifUpgradeEndpointPortMap</p></td>
</tr>
</tbody>
</table>


## Remarks

Cannot use the insert\_recordset method as insert method of the AifPortActionPolicy table is overridden.

  


