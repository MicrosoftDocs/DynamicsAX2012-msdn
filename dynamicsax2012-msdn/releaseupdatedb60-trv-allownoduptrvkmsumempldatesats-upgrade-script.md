---
title: ReleaseUpdateDB60_Trv.allowNoDupTrvKmSumEmplDateSats Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.allowNoDupTrvKmSumEmplDateSats Upgrade Script
ms:assetid: 560fa2bf-5e40-70ce-af9f-763908f36392
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736178(v=AX.60)
ms:contentKeyID: 49708353
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.allowNoDupTrvKmSumEmplDateSats Upgrade Script 


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
<td><p>allowNoDupTrvKmSumEmplDateSats</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EmplDateSats index to not allow for duplicate records.</p></td>
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
<td><p>TrvKmSum</p></td>
</tr>
</tbody>
</table>


## Remarks

Resets the EmplDateSats index to not allow for duplicate records in the Worker field.

  


