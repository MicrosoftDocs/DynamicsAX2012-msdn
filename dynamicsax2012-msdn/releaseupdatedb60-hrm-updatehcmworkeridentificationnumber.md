﻿---
title: ReleaseUpdateDB60_HRM.updateHcmWorkerIdentificationNumber
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmWorkerIdentificationNumber
ms:assetid: 183503f3-eadc-a8cb-caca-beb220ef8175
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718598(v=AX.60)
ms:contentKeyID: 49706879
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmWorkerIdentificationNumber [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateHcmWorkerIdentificationNumber</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmWorkerIdentificationNumber&lt;/c&gt; table from the &lt;c&gt;HRMEmplIdentification&lt;/c&gt; table.</p></td>
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
<td><p>HcmWorkerIdentificationNumber</p></td>
</tr>
<tr class="even">
<td><p>HRMEmplIdentification</p></td>
</tr>
<tr class="odd">
<td><p>HRMi9IssuingAuthority</p></td>
</tr>
<tr class="even">
<td><p>HRMIdentificationType</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>Worker\</c\> field in the \<c\>HcmWorkerIdentificationNumber\</c\> table is the foreign key to the \<c\>HcmWorker\</c\> table. The \<c\>IssuingAgency\</c\> field in the \<c\>HcmWorkerIdentificationNumber\</c\> table is the foreign key to the \<c\>HcmIssuingAgency\</c\> table. The \<c\>IdentificationType\</c\> field in the \<c\>HcmWorkerIdentificationNumber\</c\> table is the foreign key to the \<c\>IdentificationType\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMEmplIdentification</p></th>
<th><p>To Table: HcmWorkerIdentificationNumber</p></th>
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
<td><p>HcmWorkerIdentificationNumber</p></td>
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
<td><p>HRMEmplIdentification</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

