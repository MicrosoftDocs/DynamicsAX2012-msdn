---
title: ReleaseUpdateDB60_Payroll.updatePayrollPositionDetails Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollPositionDetails Upgrade Script
ms:assetid: 3cdc0e48-4a0e-f97a-65e0-aa9b78ab124a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685316(v=AX.60)
ms:contentKeyID: 49707768
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollPositionDetails Upgrade Script 


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
<td><p>updatePayrollPositionDetails</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollPositionDetails table from the DEL_HRPPartyPositionTable, DEL_EmplTable and PayrollPayCycle tables.</p></td>
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
<td><p>PAYROLLPOSITIONDETAILS</p></td>
</tr>
<tr class="even">
<td><p>HCMPOSITION</p></td>
</tr>
<tr class="odd">
<td><p>DEL_HRPPARTYPOSITIONTABLERELATIONSHIP</p></td>
</tr>
<tr class="even">
<td><p>DEL_EMPLTABLE</p></td>
</tr>
<tr class="odd">
<td><p>PRLEMPLOYEEUSFEDERALTAXSETUP</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLPAYCYCLE</p></td>
</tr>
<tr class="odd">
<td><p>PRLEMPLGROUP</p></td>
</tr>
<tr class="even">
<td><p>DEL_HRPPARTYJOBTABLERELATIONSHIP</p></td>
</tr>
<tr class="odd">
<td><p>HcmEmploymentLeave</p></td>
</tr>
<tr class="even">
<td><p>HcmLeaveType</p></td>
</tr>
<tr class="odd">
<td><p>WorkCalendarTable</p></td>
</tr>
<tr class="even">
<td><p>WorkCalendarDate</p></td>
</tr>
<tr class="odd">
<td><p>WorkCalendarDateLine</p></td>
</tr>
<tr class="even">
<td><p>WorkTimeTable</p></td>
</tr>
<tr class="odd">
<td><p>WorkTimeLine</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will create a record in the PayrollPositionDetails table from the fields in the DEL\_EmplTable table, and the HcmPosition table. Records in the PayrollPositionDetails table will only be created if the "active" or "expired" DEL\_HRPPartyTableRelationship record exists that is associated to the identified DEL\_EmplTable table record. The schedules are created and assigned to the schedule field of the PayrollPositionDetails table when a schedule is needed for the GenerateEarningsFromSchedule field of the PayrollPositionDetails table is set to true or a record in the HcmEmploymentLeave table is created for the worker assigned to position.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HCMPosition</p></th>
<th><p>To Table: PayrollPositionDetails</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecID</p></td>
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
<th><p>From Table: Del_EmplTable</p></th>
<th><p>To Table: PayrollPositionDetails</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_PRLNormHrs</p></td>
<td><p>PayrollNormalHours</p></td>
</tr>
<tr class="even">
<td><p>DEL_PRLOThrs</p></td>
<td><p>PayrollOvertimeHours</p></td>
</tr>
<tr class="odd">
<td><p>DataAreaID</p></td>
<td><p>PaidByLegalEntity</p></td>
</tr>
<tr class="even">
<td><p>PRLCompanyOfficer</p></td>
<td><p>IsCompanyOfficer</p></td>
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
<th><p>From Table: PayrollPayCycle</p></th>
<th><p>To Table: PayrollPositionDetails</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>PayCycle</p></td>
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
<td><p>PayrollPositionDetails</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  


