---
title: ReleaseUpdateDB60_Ledger.allowDupLedgerOpeningTable_ESShMnAcct Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupLedgerOpeningTable_ESShMnAcct Upgrade Script
ms:assetid: eb4a758c-6be4-9adf-65e6-7d2e24719bd8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719911(v=AX.60)
ms:contentKeyID: 49711983
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupLedgerOpeningTable\_ESShMnAcct Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>allowDupLedgerOpeningTable_ESShMnAcct</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ShMnAcctIdx index in the LedgerOpeningTable_ES table to allow for duplicate records.</p></td>
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
<td><p>LedgerOpeningTable_ES</p></td>
</tr>
</tbody>
</table>


## Remarks

The AccountNum field is replaced with the new MainAccount field in the ShMnAcctIdx unique index. Initially this field contains no value. So the index is set to allow for duplicates before the field is updated with the value of the record ID field in the MainAccount table.

  


