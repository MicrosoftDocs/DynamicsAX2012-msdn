---
title: ReleaseUpdateDB60_HRM.updateHcmi9Document Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmi9Document Upgrade Script
ms:assetid: 09bd213d-6fd3-7211-44a9-22fb6232ed26
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735596(v=AX.60)
ms:contentKeyID: 49706508
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmi9Document Upgrade Script 


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
<td><p>updateHcmi9Document</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the Hcmi9Document table from the HRMi9Document table.</p></td>
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
<td><p>CompanyInfo</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
</tr>
<tr class="odd">
<td><p>Hcmi9Document</p></td>
</tr>
<tr class="even">
<td><p>HcmWorker</p></td>
</tr>
<tr class="odd">
<td><p>HCMWorkerAffiliation</p></td>
</tr>
<tr class="even">
<td><p>HRMi9Document</p></td>
</tr>
<tr class="odd">
<td><p>HRMi9DocumentType</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddressZipCode</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company. The EmployeeAffiliation field in the table is the foreign key to the HcmEmployeeAffiliation table. The VerifiedBy field in the table is the foreign key to the HcmWorker table. The PreparerZipCode field in the table is the foreign key to the LogisticsAddressZipCode table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMi9Document</p></th>
<th><p>To Table: Hcmi9Document</p></th>
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
<p>-or- Base Enum*</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hcmi9Document</p></td>
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
<td><p>HRMi9Document</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

