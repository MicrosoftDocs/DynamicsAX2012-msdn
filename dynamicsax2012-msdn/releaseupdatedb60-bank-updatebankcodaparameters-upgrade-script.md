---
title: ReleaseUpdateDB60_Bank.updateBankCodaParameters Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.updateBankCodaParameters Upgrade Script
ms:assetid: b40a6d88-9fa6-2417-7982-ba6e305864f8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736950(v=AX.60)
ms:contentKeyID: 49710634
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.updateBankCodaParameters Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Bank</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBankCodaParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The ledger account fields AccountNum, ProfitAccountNum and toAccountNum are converted to the ledger dimension LedgerDimension, ProfitLedgerDimension and LossLedgerDimension fields.</p></td>
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
<td><p>BankCodaParameters</p></td>
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
<td><p>BankCodaParameters</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>BankCodaParameters</p></td>
<td><p>ProfitLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>BankCodaParameters</p></td>
<td><p>LossLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
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
<td><p>BankCodaParameters</p></td>
<td><p>AccountNum</p></td>
</tr>
<tr class="even">
<td><p>BankCodaParameters</p></td>
<td><p>ProfitAccountNum</p></td>
</tr>
<tr class="odd">
<td><p>BankCodaParameters</p></td>
<td><p>LossAccountNum</p></td>
</tr>
</tbody>
</table>

  


