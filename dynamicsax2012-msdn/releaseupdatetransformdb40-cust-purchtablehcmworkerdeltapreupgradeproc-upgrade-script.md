﻿---
title: ReleaseUpdateTransformDB40_Cust.purchTableHcmWorkerDeltaPreUpgradeProc Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Cust.purchTableHcmWorkerDeltaPreUpgradeProc Upgrade Script
ms:assetid: 97318344-f53f-721f-f1cf-83640f29e200
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686209(v=AX.60)
ms:contentKeyID: 49709912
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Cust.purchTableHcmWorkerDeltaPreUpgradeProc Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>purchTableHcmWorkerDeltaPreUpgradeProc</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the PurchPlacer field to the WorkerPurchPlacer field and from the Requisitioner field to the Requester field in the PurchTable table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>PurchTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The upgrade converts employee data to a new HRM model.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchTable</p></th>
<th><p>To Table: Shadow_PurchTableHcmWorker</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchPlacer</p></td>
<td><p>WorkerPurchPlacer</p></td>
</tr>
<tr class="even">
<td><p>Requisitioner</p></td>
<td><p>Requester</p></td>
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
<td><p>Shadow_PurchTableHcmWorker</p></td>
<td><p>WorkerPurchPlacer</p></td>
<td><p>PurchPlacer</p></td>
</tr>
<tr class="even">
<td><p>Shadow_PurchTableHcmWorker</p></td>
<td><p>Requester</p></td>
<td><p>PurchRequester</p></td>
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
<td><p>PurchTable</p></td>
<td><p>PurchPlacer</p></td>
</tr>
<tr class="even">
<td><p>PurchTable</p></td>
<td><p>Requisitioner</p></td>
</tr>
</tbody>
</table>

  


