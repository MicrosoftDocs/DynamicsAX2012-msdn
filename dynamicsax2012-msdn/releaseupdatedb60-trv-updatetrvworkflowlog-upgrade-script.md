---
title: ReleaseUpdateDB60_Trv.updateTrvWorkflowLog Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvWorkflowLog Upgrade Script
ms:assetid: 6d7d947e-4731-8687-ed07-f4c543090a1a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685708(v=AX.60)
ms:contentKeyID: 49708910
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvWorkflowLog Upgrade Script 


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
<td><p>updateTrvWorkflowLog</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates data from the DEL_ApprovedBy field to the ApprovedByWorker field and the DEL_RejectedBy field to the RejectedByWorker field in the TrvWorkflowLog table.</p></td>
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
<td><p>TrvWorkflowLog</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade script is needed to convert the employee ID to the new worker for Microsoft Dynamics AX 2012 as part of the HCM uptake for Expense Management.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvWorkflowLog</p></th>
<th><p>To Table: TrvWorkflowLog</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_ApprovedBy</p></td>
<td><p>ApprovedByWorker</p></td>
</tr>
<tr class="even">
<td><p>DEL_RejectedBy</p></td>
<td><p>RejectedByWorker</p></td>
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
<td><p>TrvWorkflowLog</p></td>
<td><p>ApprovedByWorker</p></td>
<td><p>TrvHcmWorkerRecId</p></td>
</tr>
<tr class="even">
<td><p>TrvWorkflowLog</p></td>
<td><p>RejectedByWorker</p></td>
<td><p>TrvHcmWorkerRecId</p></td>
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
<td><p>TrvWorkflowLog</p></td>
<td><p>DEL_ApprovedBy</p></td>
</tr>
<tr class="even">
<td><p>TrvWorkflowLog</p></td>
<td><p>DEL_RejectedBy</p></td>
</tr>
</tbody>
</table>

  


