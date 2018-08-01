---
title: ReleaseUpdateDB41_Bank.updateBankStmtISOAccountStatement Upgrade Script
TOCTitle: ReleaseUpdateDB41_Bank.updateBankStmtISOAccountStatement Upgrade Script
ms:assetid: 3305d393-efc2-011a-6653-56f9dbe7f82b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685091(v=AX.60)
ms:contentKeyID: 49707545
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Bank.updateBankStmtISOAccountStatement Upgrade Script 


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
<td><p>updateBankStmtISOAccountStatement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updatess the AccountStatementDate field from the BankAccountStatement table to the ToDateTime field of the BankStmtISOAccountStatement table.</p></td>
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
<td><p>BankStmtISOAccountStatement</p></td>
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
<th><p>From Table: BankAccountStatement</p></th>
<th><p>To Table: BankStmtISOAccountStatement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountStatementDate</p></td>
<td><p>ToDateTime</p></td>
</tr>
</tbody>
</table>

  


