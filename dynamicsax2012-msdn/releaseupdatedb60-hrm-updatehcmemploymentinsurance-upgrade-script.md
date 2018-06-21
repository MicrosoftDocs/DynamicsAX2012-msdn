﻿---
title: ReleaseUpdateDB60_HRM.updateHcmEmploymentInsurance Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHcmEmploymentInsurance Upgrade Script
ms:assetid: 7da16ec6-50b7-b385-ec1f-98dcd2347f8d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719480(v=AX.60)
ms:contentKeyID: 49709270
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHcmEmploymentInsurance Upgrade Script [AX 2012]


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
<td><p>updateHcmEmploymentInsurance</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmEmploymentInsurance table from the DEL_HRMInsurance table.</p></td>
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
<td><p>HcmEmploymentInsurance</p></td>
</tr>
</tbody>
</table>


## Remarks

The Employment field in the HcmEmploymentInsurance table is the foreign key to the HcmEmployment table. The InsuranceType field in the HcmEmploymentInsurance table is the foreign key to the DEL\_HcmInsuranceType table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_HRMInsurance</p></th>
<th><p>To Table: HcmEmploymentInsurance</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amount</p></td>
<td><p>Amount</p></td>
</tr>
<tr class="even">
<td><p>Percentage</p></td>
<td><p>Percentage</p></td>
</tr>
<tr class="odd">
<td><p>FromDate</p></td>
<td><p>FromDate</p></td>
</tr>
<tr class="even">
<td><p>PayedBy</p></td>
<td><p>PayedBy</p></td>
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
<th><p>From Table: DEL_HRMInsuranceType</p></th>
<th><p>To Table: HcmEmploymentInsurance</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MappingRecId</p></td>
<td><p>InsuranceType</p></td>
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
<th><p>From Table: HcmEmployment</p></th>
<th><p>To Table: HcmEmploymentInsurance</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Employment</p></td>
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
<td><p>DEL_HRMInsurance</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

