﻿---
title: ReleaseUpdateDB60_Proj.updateProjBegBalJournalTrans_CostSales Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjBegBalJournalTrans_CostSales Upgrade Script
ms:assetid: 63a25521-a5e7-fe7a-c440-c4ce21e9b45d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719139(v=AX.60)
ms:contentKeyID: 49708678
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjBegBalJournalTrans\_CostSales Upgrade Script 


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
<td><p>updateProjBegBalJournalTrans_CostSales</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the ProjTransCode field to the ProjTransCodeWorker field in the ProjBegBalJournalTrans_CostSales table.</p></td>
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
<td><p>ProjBegBalJournalTrans_CostSales</p></td>
</tr>
</tbody>
</table>


## Remarks

HCMWorker table and associated tables have replaced the Employee table, that is the EmplTable, and the associated tables in Microsoft Dynamics AX 2012. This transition requires an upgrade.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjBegBalJournalTrans_CostSales</p></th>
<th><p>To Table: ProjBegBalJournalTrans_CostSales</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ProjTransCode</p></td>
<td><p>ProjTransCodeWorker</p></td>
</tr>
</tbody>
</table>


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
<td><p>ProjBegBalJournalTrans_CostSales</p></td>
<td><p>ProjTransCodeWorker</p></td>
<td><p>ProjWorkerRecId</p></td>
</tr>
</tbody>
</table>

  


