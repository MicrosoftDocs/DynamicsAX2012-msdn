---
title: ReleaseUpdateDB60_Proj.updateFundingSearchParameter Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateFundingSearchParameter Upgrade Script
ms:assetid: eee4277b-6c07-df84-6155-61a9fb3cdd00
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720027(v=AX.60)
ms:contentKeyID: 49712079
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateFundingSearchParameter Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateFundingSearchParameter</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the default funding rule search criteria that is used by advanced contracts.</p></td>
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
<td><p>Project</p></td>
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
<td><p>ProjFundingSearchParameter</p></td>
</tr>
</tbody>
</table>


## Remarks

One entry will be created for each of the ProjFundingSearchCriteria enumeration values.

## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ProjFundingSearchParameter</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


