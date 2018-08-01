---
title: ReleaseUpdateDB60_Proj.updateProjTableWorker Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjTableWorker Upgrade Script
ms:assetid: b8103641-b4d1-11b2-84e8-70392dd6967c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737074(v=AX.60)
ms:contentKeyID: 49710756
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjTableWorker Upgrade Script 


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
<td><p>updateProjTableWorker</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_ResponsibleFinancial field to the WorkerResponsibleFinancial field, the DEL_Responsible field to the WorkerResponsible field, and the DEL_ResponsibleSales field to the WorkerResponsibleSales field in the ProjTable table.</p></td>
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
<td><p>ProjTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The HCMWorker table and associated tables have replaced the Employee table, that is the EmplTable table, and associated tables in Microsoft Dynamics AX 2012. This transition requires an upgrade.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjTable</p></th>
<th><p>To Table: ProjTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_ResponsibleFinancial</p></td>
<td><p>WorkerResponsibleFinancial</p></td>
</tr>
<tr class="even">
<td><p>DEL_Responsible</p></td>
<td><p>WorkerResponsible</p></td>
</tr>
<tr class="odd">
<td><p>DEL_ResponsibleSales</p></td>
<td><p>WorkerResponsibleSales</p></td>
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
<td><p>ProjTable</p></td>
<td><p>WorkerResponsibleFinancial</p></td>
<td><p>ProjWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>ProjTable</p></td>
<td><p>WorkerResponsible</p></td>
<td><p>ProjWorkerRecId</p></td>
</tr>
<tr class="odd">
<td><p>ProjTable</p></td>
<td><p>WorkerResponsibleSales</p></td>
<td><p>ProjWorkerRecId</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ProjTable</p></td>
<td><p>DEL_ResponsibleFinancial</p></td>
</tr>
<tr class="even">
<td><p>ProjTable</p></td>
<td><p>DEL_Responsible</p></td>
</tr>
<tr class="odd">
<td><p>ProjTable</p></td>
<td><p>DEL_ResponsibleSales</p></td>
</tr>
</tbody>
</table>

  


