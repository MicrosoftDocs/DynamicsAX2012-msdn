---
title: ReleaseUpdateDB60_Prod.updateWorkPeriodTemplate Upgrade Script
TOCTitle: ReleaseUpdateDB60_Prod.updateWorkPeriodTemplate Upgrade Script
ms:assetid: 04f7df71-b937-babf-1dc8-8970670df21e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684713(v=AX.60)
ms:contentKeyID: 49706409
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Prod.updateWorkPeriodTemplate Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateWorkPeriodTemplate</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates two new period template definitions for each legal entity.</p></td>
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
<td><p>WorkPeriodTemplate</p></td>
</tr>
<tr class="even">
<td><p>WorkPeriodTemplateLine</p></td>
</tr>
</tbody>
</table>


## Remarks

One period template that contains 10 weeks is created and one period template that contains 6 months is created.

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
<td><p>WorkPeriodTemplate</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>WorkPeriodTemplateLine</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


