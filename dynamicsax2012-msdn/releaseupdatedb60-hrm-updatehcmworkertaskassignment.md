---
title: ReleaseUpdateDB60_HRM.updateHcmWorkerTaskAssignment
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmWorkerTaskAssignment
ms:assetid: e909d6dd-2712-b832-a489-10b57941cf8b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719856(v=AX.60)
ms:contentKeyID: 49711929
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmWorkerTaskAssignment 


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
<td><p>updateHcmWorkerTaskAssignment</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;HcmWorkerTaskAssignment&lt;/c&gt; table from the &lt;c&gt;EmplTask&lt;/c&gt; table.</p></td>
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
<td><p>EmplTask</p></td>
</tr>
<tr class="odd">
<td><p>HcmWorker</p></td>
</tr>
<tr class="even">
<td><p>HcmWorkerTask</p></td>
</tr>
<tr class="odd">
<td><p>HcmWorkerTaskAssignment</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>Worker\</c\> field in the \<c\>HcmWorkerTaskAssignment\</c\> table is the foreign key to the \<c\>HcmWorker\</c\> table. The \<c\>WorkerTask\</c\> field in the \<c\>HcmWorkerTaskAssignment\</c\> table is the foreign key to the \<c\>HcmWorkerTask\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: EmplTask</p></th>
<th><p>To Table: HcmWorkerTaskAssignment</p></th>
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
<td><p>HcmWorkerTaskAssignment</p></td>
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
<td><p>EmplTask</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


