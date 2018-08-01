---
title: ReleaseUpdateDB60_Bank.updateBankDepositSource Upgrade Script
TOCTitle: ReleaseUpdateDB60_Bank.updateBankDepositSource Upgrade Script
ms:assetid: 1e95e669-c1b8-cb44-51cd-7e5ee1ad996c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684845(v=AX.60)
ms:contentKeyID: 49707048
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Bank.updateBankDepositSource Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateBankDepositSource</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the source and reversal source fields in the BankDeposit table, and populates the new BankDepositDocument table.</p></td>
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
<td><p>BANKDEPOSIT</p></td>
</tr>
<tr class="even">
<td><p>LEDGERJOURNALTRANS</p></td>
</tr>
<tr class="odd">
<td><p>BANKACCOUNTTRANS</p></td>
</tr>
<tr class="even">
<td><p>BANKDEPOSITDOCUMENT</p></td>
</tr>
</tbody>
</table>

  


