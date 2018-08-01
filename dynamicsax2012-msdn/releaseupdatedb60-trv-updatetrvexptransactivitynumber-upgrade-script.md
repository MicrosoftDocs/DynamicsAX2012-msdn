---
title: ReleaseUpdateDB60_Trv.updateTrvExpTransActivityNumber Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvExpTransActivityNumber Upgrade Script
ms:assetid: 967e4024-d53d-806e-95df-2778a451811a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686193(v=AX.60)
ms:contentKeyID: 49709897
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvExpTransActivityNumber Upgrade Script 


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
<td><p>updateTrvExpTransActivityNumber</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Moves the ActivityNumber field from the DEL_TrvExpTrans_Proj table to the new ProjActivityNumber field in the TrvExpTrans table.</p></td>
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
<td><p>TrvExpTrans</p></td>
</tr>
<tr class="even">
<td><p>DEL_TrvExpTrans_Proj</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvExpTrans_Proj</p></th>
<th><p>To Table: TrvExpTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ActivityNumber</p></td>
<td><p>ProjActivityNumber</p></td>
</tr>
</tbody>
</table>

  


