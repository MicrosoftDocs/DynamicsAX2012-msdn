---
title: ReleaseUpdateTransformDB40_Cust.salesOrderEntryStatDeltaPreUpgradeProc Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Cust.salesOrderEntryStatDeltaPreUpgradeProc Upgrade Script
ms:assetid: 35c47d0d-e90f-6928-ef1c-4501ee41db35
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685154(v=AX.60)
ms:contentKeyID: 49707607
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Cust.salesOrderEntryStatDeltaPreUpgradeProc Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>salesOrderEntryStatDeltaPreUpgradeProc</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms person data from the &lt;c&gt;SalesResponsible&lt;/c&gt; field to the &lt;c&gt;WorkerSalesResponsible&lt;/c&gt; field in the &lt;c&gt;SalesOrderEntryStatistics&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>4.01</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>SalesOrderEntryStatistics</p></td>
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
<th><p>From Table: SalesOrderEntryStatistics</p></th>
<th><p>To Table: Shadow_SalesOrderEntryStatisticsHcmWrk</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SalesResponsible</p></td>
<td><p>WorkerSalesResponsible</p></td>
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
<td><p>SalesOrderEntryStatisticsHcmWrk</p></td>
<td><p>WorkerSalesResponsible</p></td>
<td><p>WorkerSalesResponsible</p></td>
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
<td><p>SalesOrderEntryStatistics</p></td>
<td><p>SalesResponsible</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

