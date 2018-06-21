---
title: ReleaseUpdateDB60_Cust.allowDupBankCustPaymModeBankAccountsPaym Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.allowDupBankCustPaymModeBankAccountsPaym Upgrade Script
ms:assetid: e00c25d8-5b5b-c540-cf46-a102c288ec71
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737264(v=AX.60)
ms:contentKeyID: 49711706
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.allowDupBankCustPaymModeBankAccountsPaym Upgrade Script [AX 2012]


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
<td><p>allowDupBankCustPaymModeBankAccountsPaym</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Disables a unique index to allow for duplicates records in the BankCustPaymModeBankAccounts table.</p></td>
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

The Dimension field is replaced with the new DefaultDimension field in the PaymModeCurrencyIdx unique index. Initially this field contains no value. So the index is set to allow for duplicates before the field is updated with the value that is based on the del\_Dimension field in the BankCustPaymModeBankAccounts table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

