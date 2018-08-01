---
title: ReleaseUpdateDB60_Payroll.updatePayrollWorkerPositionEarningCode Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollWorkerPositionEarningCode Upgrade Script
ms:assetid: a951cda7-9332-1a21-7944-d54546b6051e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686426(v=AX.60)
ms:contentKeyID: 49710382
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollWorkerPositionEarningCode Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Payroll</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePayrollWorkerPositionEarningCode</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records in the PayrollWorkerPositionEarningCode table from the DEL_HRPPartyJobTableRelationship table, the DEL_EmplTable table and the PRLEmployeePayElements table. This script also inserts the record in the PayrollWorkerPositionEarningFrequency table.</p></td>
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
<td><p>Payroll</p></td>
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
<td><p>PAYROLLWORKERPOSITIONEARNINGCODE</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLWORKERPOSITIONEARNINGFREQUENCY</p></td>
</tr>
<tr class="odd">
<td><p>HCMPOSITION</p></td>
</tr>
<tr class="even">
<td><p>DEL_HRPPARTYPOSITIONTABLERELATIONSHIP</p></td>
</tr>
<tr class="odd">
<td><p>DEL_EMPLTABLE</p></td>
</tr>
<tr class="even">
<td><p>PRLEMPLOYEEUSFEDERALTAXSETUP</p></td>
</tr>
<tr class="odd">
<td><p>DEL_HRPPARTYJOBTABLERELATIONSHIP</p></td>
</tr>
<tr class="even">
<td><p>PRLEMPLOYEEPAYELEMENTS</p></td>
</tr>
<tr class="odd">
<td><p>PRLPAYELEMENTS</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will create record in the PayrollWorkerPositionEarningCode table from the fields in the PRLPayElements table, the PRLEmployeePayElements table and the HcmPosition table. Records in the PayrollWorkerPositionEarningCode table will only be created if the active or expired DEL\_HRPPartyTableRelationship record exists that is associated to the specified DEL\_EmplTable record. This upgrade will also create multiple versions if there are multiple PRLEmployeePayElements records for one position ID.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HcmPosition</p></th>
<th><p>To Table: PayrollWorkerPositionEarningCode</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Position</p></td>
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
<th><p>From Table: PRLPayElements</p></th>
<th><p>To Table: PayrollWorkerPositionEarningCode</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_MappingRecId</p></td>
<td><p>EarningCode</p></td>
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
<th><p>From Table: PRLEmployeePayElements</p></th>
<th><p>To Table: PayrollWorkerPositionEarningCode</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayElementDate</p></td>
<td><p>ValidFrom</p></td>
</tr>
<tr class="even">
<td><p>PayElementDate</p></td>
<td><p>ValidTo</p></td>
</tr>
<tr class="odd">
<td><p>HourlyRate</p></td>
<td><p>Formula</p></td>
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
<th><p>From Table: DEL_EmplTable</p></th>
<th><p>To Table: PayrollWorkerPositionEarningCode</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Party</p></td>
<td><p>Worker</p></td>
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
<th><p>From Table: PayrollWorkerPositionEarningCode</p></th>
<th><p>To Table: PayrollWorkerPositionEarningFrequency</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>WorkerPositionEarningCode</p></td>
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
<td><p>PayrollWorkerPositionEarningCode</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


