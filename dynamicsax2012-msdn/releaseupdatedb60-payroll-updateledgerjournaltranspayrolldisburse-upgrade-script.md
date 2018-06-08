---
title: ReleaseUpdateDB60_Payroll.updateLedgerJournalTransPayrollDisburse Upgrade Script
TOCTitle: ReleaseUpdateDB60_Payroll.updateLedgerJournalTransPayrollDisburse Upgrade Script
ms:assetid: 8f1b7152-f356-0e11-24f0-b46615e752ae
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736526(v=AX.60)
ms:contentKeyID: 49709715
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Payroll.updateLedgerJournalTransPayrollDisburse Upgrade Script 


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
<td><p>updateLedgerJournalTransPayrollDisburse</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Inserts records into the LedgerJournalTransPayrollDisbursement table from the LedgerJournalTrans, PRLEmployeePayElementsTransPosted, and DEL_PRLEmplBankAccount tables.</p></td>
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
<td><p>LedgerJournalTransPayrollDisbursement</p></td>
</tr>
<tr class="even">
<td><p>LedgerJournalTrans</p></td>
</tr>
<tr class="odd">
<td><p>PRLEmployeePayElementsTransPosted</p></td>
</tr>
<tr class="even">
<td><p>DEL_PRLEmplBankAccount</p></td>
</tr>
</tbody>
</table>


## Remarks

Inserts records into the LedgerJournalTransPayrollDisbursement table from the LedgerJournalTrans, PRLEmployeePayElementsTransPosted, and DEL\_PRLEmplBankAccount tables. The PayStatement field is the record ID of the posted payment, the RecId field is the LedgerJournalTrans record ID of that posted transaction and the WorkerBankAccount value is the bank account record ID where there exists a PRLDDNumber and CustVendBankAccountId value in the LedgerJournalTrans table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PRLEmployeePayElementsTransPosted</p></th>
<th><p>To Table: LedgerJournalTransPayrollDisbursement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MappingRecId</p></td>
<td><p>PayStatement</p></td>
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
<th><p>From Table: LedgerJournalTrans</p></th>
<th><p>To Table: LedgerJournalTransPayrollDisbursement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>RefRecId</p></td>
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
<th><p>From Table: DEL_PRLEmplBankAccount</p></th>
<th><p>To Table: LedgerJournalTransPayrollDisbursement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>WorkerBankAccount</p></td>
<td><p>WorkerBankAccount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

