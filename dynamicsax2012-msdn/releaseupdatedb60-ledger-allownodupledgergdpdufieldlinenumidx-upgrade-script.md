---
title: ReleaseUpdateDB60_Ledger.allowNoDupLedgerGDPdUFieldLineNumIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupLedgerGDPdUFieldLineNumIdx Upgrade Script
ms:assetid: 05009aeb-fd4c-4a3f-8490-dd2ace56298c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684711(v=AX.60)
ms:contentKeyID: 49706407
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupLedgerGDPdUFieldLineNumIdx Upgrade Script 


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
<td><p>allowNoDupLedgerGDPdUFieldLineNumIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the LineNumIdx index in the table LedgerGDPdUField table not to allow for duplicate records.</p></td>
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
<td><p>LedgerGDPdUField</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the LedgerGDPdUTable surrogate key field with the value of the RecId field of the LedgerGDPdUTable table, the LineNumIdx index is reset not to allow for duplicate records.

  


