---
title: ReleaseUpdateDB60_HRM.updateHcmi9DocumentType
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmi9DocumentType
ms:assetid: e1c91c48-0293-3e26-4e81-7bf5b4413e0d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737316(v=AX.60)
ms:contentKeyID: 49711758
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmi9DocumentType 


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
<td><p>updateHcmi9DocumentType</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the &lt;c&gt;Hcmi9DocumentType&lt;/c&gt; table from the &lt;c&gt;HRMi9DocumentType&lt;/c&gt; table.</p></td>
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
<td><p>Hcmi9DocumentType</p></td>
</tr>
<tr class="even">
<td><p>HRMi9DocumentType</p></td>
</tr>
<tr class="odd">
<td><p>HRMi9IssuingAuthority</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending the \<c\>DataAreaId\</c\> field to the \<c\>DocumentTypeId\</c\> field of the \<c\>HRMi9DocumentType\</c\> table to create new, unique identifiers for the \<c\>Hcmi9DocumentType\</c\> table when multiple companies exist. If only one company exists, the \<c\>DataAreaId\</c\> field will not be appended. The \<c\>IssuingAgency\</c\> field in the \<c\>Hcmi9DocumentType\</c\> table is the foreign key to the \<c\>HcmIssuingAgency\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMi9DocumentType</p></th>
<th><p>To Table: Hcmi9DocumentType</p></th>
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
<td><p>Hcmi9DocumentType</p></td>
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
<td><p>HRMi9DocumentType</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


