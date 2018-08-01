---
title: ReleaseUpdateDB60_HRM.updateHcmIncomeTaxCode Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmIncomeTaxCode Upgrade Script
ms:assetid: 0bb951d7-2a98-1274-1913-ed5c6a7844d4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735655(v=AX.60)
ms:contentKeyID: 49706566
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmIncomeTaxCode Upgrade Script 


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
<td><p>updateHcmIncomeTaxCode</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmIncomeTaxCode table from the HRMIncomeTaxCode table.</p></td>
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
<td><p>HcmIncomeTaxCode</p></td>
</tr>
<tr class="even">
<td><p>HRMIncomeTaxCode</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will discard duplicate records if the HrmIncomeTaxCodeId field and the Description field of the HRMIncomeTaxCode table are identical. The new unique identifier IncomeTaxCodeId field of the HcmIncomeTaxCode table combines the HrmIncomeTaxCodeId field and the DataAreaId field of the HRMIncomeTaxCode table from the first record found. All records found that are identified as duplicates in other companies will be discarded. If only one company exists, the DataAreaId field will not be appended.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMIncomeTaxCode</p></th>
<th><p>To Table: HcmIncomeTaxCode</p></th>
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
<td><p>HcmIncomeTaxCode</p></td>
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
<td><p>HRMIncomeTaxCode</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


