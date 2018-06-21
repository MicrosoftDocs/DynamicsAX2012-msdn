---
title: ReleaseUpdateDB60_Payroll.updatePayrollPayCycle Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollPayCycle Upgrade Script
ms:assetid: 3afb339d-2a79-870f-0a9e-6f801246f006
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685271(v=AX.60)
ms:contentKeyID: 49707721
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollPayCycle Upgrade Script [AX 2012]


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
<td><p>updatePayrollPayCycle</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollPayCycle table from the DEL_PRLPayPeriodMaster table.</p></td>
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
<td><p>PAYROLLPAYCYCLE</p></td>
</tr>
<tr class="even">
<td><p>DEL_PRLPAYROLLPERIODMASTER</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will retain the data of each company by appending the DataAreaId field to the PayrollPeriodId field of the DEL\_PRLPayrollPeriodMaster table to create new, unique identifiers for the PayrollPayCycle table when multiple companies exist. If only one company exists, the DataAreaId field will not be appended. The enum values for the TimePeriod field differ from the values of the PRLPayPeriodEnum enumeration. To correctly map the existing value to the new value, one is added to the TimePeriod field value during the upgrade.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_PRLPayrollPeriodMaster</p></th>
<th><p>To Table: PayrollPayCycle</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayrollPeriodId</p></td>
<td><p>PayCycleID</p></td>
</tr>
<tr class="even">
<td><p>Description</p></td>
<td><p>Description</p></td>
</tr>
<tr class="odd">
<td><p>PRLPayPeriodEnum</p></td>
<td><p>TimePeriod</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

