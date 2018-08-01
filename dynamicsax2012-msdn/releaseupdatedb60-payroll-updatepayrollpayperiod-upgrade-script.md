---
title: ReleaseUpdateDB60_Payroll.updatePayrollPayPeriod Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollPayPeriod Upgrade Script
ms:assetid: 851a0223-4673-d299-e453-096c9f25b645
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686020(v=AX.60)
ms:contentKeyID: 49709471
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollPayPeriod Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updatePayrollPayPeriod</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the PayrollPayPeriod table from the DEL_PRLPayrollPeriod table.</p></td>
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
<td><p>DEL_PRLPAYROLLPERIODMASTER</p></td>
</tr>
<tr class="even">
<td><p>PAYROLLPAYPERIOD</p></td>
</tr>
<tr class="odd">
<td><p>DEL_PRLPAYROLLPERIOD</p></td>
</tr>
<tr class="even">
<td><p>PRLEMPLOYEEPAYELEMENTSTRANSPOSTED</p></td>
</tr>
</tbody>
</table>


## Remarks

The PayPeriodID field of the PayrollPayPeriod table is new in this release and is part of an alternate key in the new table. The value is created by concatenating the year of the period and an integer representing the order of the period within the year.

  


