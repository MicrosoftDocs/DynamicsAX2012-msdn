---
title: ReleaseUpdateDB60_Payroll.updatePayrollPayPeriod
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollPayPeriod
ms:assetid: fc830c96-5dd7-142c-f5d3-96ea83b754e2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720108(v=AX.60)
ms:contentKeyID: 49712414
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollPayPeriod 


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
<td><p>DEL_PrlPayrollPeriodMaster</p></td>
</tr>
<tr class="even">
<td><p>PayrollPayPeriod</p></td>
</tr>
<tr class="odd">
<td><p>DEL_PrlPayrollPeriod</p></td>
</tr>
<tr class="even">
<td><p>PrlEmployeePayElementsTransposted</p></td>
</tr>
</tbody>
</table>


## Remarks

The PayPeriodID field of the PayrollPayPeriod table is new in this release and is part of an alternate key on the new table. The value is created by concatenating the year of the period with the period and an integer that represents the order of the period within the year.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

