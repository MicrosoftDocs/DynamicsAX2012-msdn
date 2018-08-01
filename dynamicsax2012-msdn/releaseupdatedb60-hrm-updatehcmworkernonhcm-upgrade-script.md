---
title: ReleaseUpdateDB60_HRM.updateHcmWorkerNonHcm Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmWorkerNonHcm Upgrade Script
ms:assetid: 0be91125-f935-c61a-8f7a-b3153fde7ebf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735665(v=AX.60)
ms:contentKeyID: 49706576
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmWorkerNonHcm Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHcmWorkerNonHcm</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the OutlookWorkerSetup table, the ProjWorkerSetup table, the PurchRFQWorkerSetup table, and the SMADispatchWorkerSetup table from the EmplTable table.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>EmplTable</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
</tr>
<tr class="odd">
<td><p>HRMPartyEmployeeRelationship</p></td>
</tr>
<tr class="even">
<td><p>OutlookWorkerSetup</p></td>
</tr>
<tr class="odd">
<td><p>ProjWorkerSetup</p></td>
</tr>
<tr class="even">
<td><p>PurchRFQWorkerSetup</p></td>
</tr>
<tr class="odd">
<td><p>SMADispatchWorkerSetup</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is identified as "not discard duplicates". The Worker field in the OutlookWorkerSetup table is the foreign key to the HcmWorker table. The Worker field in the ProjWorkerSetup table is the foreign key to the HcmWorker table. The Worker field in the PurchRFQWorkerSetup table is the foreign key to the HcmWorker table. The Worker field in the SMADispatchWorkerSetup table is the foreign key to the HcmWorker table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: OutlookWorkerSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: ProjWorkerSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: PurchRFQWorkerSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: SMADispatchWorkerSetup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
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
<td><p>OutlookWorkerSetup</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>ProjWorkerSetup</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PurchRFQWorkerSetup</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>SMADispatchWorkerSetup</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>EmplTable</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


