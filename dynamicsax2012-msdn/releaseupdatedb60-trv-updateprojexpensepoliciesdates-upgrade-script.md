﻿---
title: ReleaseUpdateDB60_Trv.updateProjExpensePoliciesDates Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateProjExpensePoliciesDates Upgrade Script
ms:assetid: 6db5a6db-a151-5d47-24c0-58d16fc6e85c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685733(v=AX.60)
ms:contentKeyID: 49708934
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateProjExpensePoliciesDates Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateProjExpensePoliciesDates</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Deletes the EffectiveDate field and add new UTCDateTime and StartDate fields.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>ProjExpPolicies</p></td>
</tr>
</tbody>
</table>


## Remarks

The EffectiveDate field is removed and the data will be converted to the UTCDateTime field and transferred to the StartDate field.

  


