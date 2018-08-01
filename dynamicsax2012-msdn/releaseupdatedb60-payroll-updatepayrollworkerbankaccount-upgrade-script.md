---
title: ReleaseUpdateDB60_Payroll.updatePayrollWorkerBankAccount Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updatePayrollWorkerBankAccount Upgrade Script
ms:assetid: a4a7302e-f1c4-2c28-e168-8394500cee47
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736788(v=AX.60)
ms:contentKeyID: 49710219
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updatePayrollWorkerBankAccount Upgrade Script [AX 2012]


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
<td><p>updatePayrollWorkerBankAccount</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the HcmWorkerBankAccount and the PayrollBankAccountDisbursement table from the DEL_PRLEmplBankAccount table.</p></td>
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
<td><p>DEL_PRLEMPLBANKACCOUNT</p></td>
</tr>
<tr class="even">
<td><p>DEL_EMPLTABLE</p></td>
</tr>
<tr class="odd">
<td><p>COMPANYINFO</p></td>
</tr>
<tr class="even">
<td><p>HCMWORKER</p></td>
</tr>
<tr class="odd">
<td><p>PAYROLLBANKACCOUNTDISBURSEMENT</p></td>
</tr>
<tr class="even">
<td><p>HCMWORKERBANKACCOUNT</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade will create records in the HcmWorkerBankAccount table and the PayrollBankAccountDisbursement table from the fields in the DEL\_PRLEmplBankAccount table. Records in the HcmWorkerBankAccount table will only be created if one does not already exist for the EmplId and AccountNum value combination. If the AccountNum value does exist, fields that were not previously initialized will be filled in from the DEL\_PRLEmplBankAccount table. The record ID of the new or found HcmWorkerBankAccount table will be used to fill in the WorkerBankAccount field of the record added to the PayrollBankAccountDisbursement table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

