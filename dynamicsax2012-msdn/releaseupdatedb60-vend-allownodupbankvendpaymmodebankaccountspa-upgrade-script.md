---
title: ReleaseUpdateDB60_Vend.allowNoDupBankVendPaymModeBankAccountsPa Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.allowNoDupBankVendPaymModeBankAccountsPa Upgrade Script
ms:assetid: 3e467cde-b5e6-06d3-7d28-9024b534fdfe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718758(v=AX.60)
ms:contentKeyID: 49707803
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.allowNoDupBankVendPaymModeBankAccountsPa Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupBankVendPaymModeBankAccountsPa</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the PaymModeCurrencyIdx index in the BankVendPaymModeBankAccounts table not to allow for duplicate records.</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>BankVendPaymModeBankAccounts</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the DefaultDimension field with the value, the PaymModeCurrencyIdx index is reset not to allow for duplicate records.

  


