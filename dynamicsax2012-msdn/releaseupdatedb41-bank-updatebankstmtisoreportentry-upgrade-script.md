---
title: ReleaseUpdateDB41_Bank.updateBankStmtISOReportEntry Upgrade Script
TOCTitle: ReleaseUpdateDB41_Bank.updateBankStmtISOReportEntry Upgrade Script
ms:assetid: a1315dfb-ffa4-d215-b40a-c6b997dd9f60
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736723(v=AX.60)
ms:contentKeyID: 49710155
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Bank.updateBankStmtISOReportEntry Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Bank</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBankStmtISOReportEntry</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TransDate field from the BankStatementTrans_CN table to the BookingDateTime field of the BankStmtISOReportEntry table.</p></td>
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
<td><p>Bank</p></td>
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
<td><p>BankStmtISOReportEntry</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: BankStatementTrans_CN</p></th>
<th><p>To Table: BankStmtISOReportEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TransDate</p></td>
<td><p>BookingDateTime</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

