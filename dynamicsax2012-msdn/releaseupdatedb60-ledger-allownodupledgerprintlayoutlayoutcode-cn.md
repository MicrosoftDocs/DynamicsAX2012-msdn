---
title: ReleaseUpdateDB60_Ledger.allowNoDupLedgerPrintLayoutLayoutCode_CN
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupLedgerPrintLayoutLayoutCode_CN
ms:assetid: 1886defe-ac4c-29ab-b8dc-3aa46e555dd0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718609(v=AX.60)
ms:contentKeyID: 49706892
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupLedgerPrintLayoutLayoutCode\_CN 


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
<td><p>allowNoDupLedgerPrintLayoutLayoutCode_CN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the LayoutCodeIdx index in the LedgerPrintLayout_CN table not to allow for duplicate records.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>LedgerPrintLayout_CN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the LedgerPrintLayout\_CN surrogate key field with the value of the RecId field of the LedgerPrintLayout\_CN table, the LayoutCodeIdx index is reset not to allow for duplicate records.

  


