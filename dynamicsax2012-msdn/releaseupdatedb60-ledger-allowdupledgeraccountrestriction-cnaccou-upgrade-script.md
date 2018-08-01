---
title: ReleaseUpdateDB60_Ledger.allowDupLedgerAccountRestriction_CNAccou Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupLedgerAccountRestriction_CNAccou Upgrade Script
ms:assetid: f3e65b3b-9bbf-50b4-3528-92fdb4e0a65d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737496(v=AX.60)
ms:contentKeyID: 49712190
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupLedgerAccountRestriction\_CNAccou Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowDupLedgerAccountRestriction_CNAccou</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the AccountRestrictionIdx index in the LedgerAccountRestriction_CN table to allow duplicate records.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>LEDGERACCOUNTRESTRICTION_CN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the LedgerAccountRestriction\_CN surrogate key field with the value of the RecId field of the LedgerAccountRestriction\_CN table, the AccountRestrictionIdx index is reset not to allow duplicate records.

  


