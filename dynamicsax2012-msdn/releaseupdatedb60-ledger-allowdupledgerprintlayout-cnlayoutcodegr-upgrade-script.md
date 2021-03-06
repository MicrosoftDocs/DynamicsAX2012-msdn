﻿---
title: ReleaseUpdateDB60_Ledger.allowDupLedgerPrintLayout_CNLayoutCodeGr Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupLedgerPrintLayout_CNLayoutCodeGr Upgrade Script
ms:assetid: 06419e53-a13a-3b2a-be88-29c83f69dae1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684739(v=AX.60)
ms:contentKeyID: 49706434
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupLedgerPrintLayout\_CNLayoutCodeGr Upgrade Script 


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
<td><p>allowDupLedgerPrintLayout_CNLayoutCodeGr</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the LayoutCodeGroupIdx index in the LedgerPrintLayout_CN table not to allow duplicate records.</p></td>
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
<td><p>LEDGERPRINTLAYOUT_CN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the LedgerPrintLayout\_CN surrogate key field with the value of the RecId field of the LedgerPrintLayout\_CN table, the LayoutCodeIdx index is reset not to allow duplicate records.

  


