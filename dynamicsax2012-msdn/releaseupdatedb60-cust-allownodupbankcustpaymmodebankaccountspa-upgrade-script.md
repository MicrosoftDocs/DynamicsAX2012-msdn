---
title: ReleaseUpdateDB60_Cust.allowNoDupBankCustPaymModeBankAccountsPa Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.allowNoDupBankCustPaymModeBankAccountsPa Upgrade Script
ms:assetid: 9d980335-c229-7d06-bb35-d7cca29fe476
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736630(v=AX.60)
ms:contentKeyID: 49710072
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.allowNoDupBankCustPaymModeBankAccountsPa Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupBankCustPaymModeBankAccountsPa</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Enables a unique index to not allow for duplicates in the BankCustPaymModeBankAccounts table.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>BankCustPaymModeBankAccounts</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the DefaultDimension field with a value, the PaymModeCurrencyIdx index is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

