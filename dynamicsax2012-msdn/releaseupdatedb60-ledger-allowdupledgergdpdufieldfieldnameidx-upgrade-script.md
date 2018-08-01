---
title: ReleaseUpdateDB60_Ledger.allowDupLedgerGDPdUFieldFieldNameIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupLedgerGDPdUFieldFieldNameIdx Upgrade Script
ms:assetid: 1271cf14-5c30-3363-2b59-2bb135c84731
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735832(v=AX.60)
ms:contentKeyID: 49706742
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupLedgerGDPdUFieldFieldNameIdx Upgrade Script 


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
<td><p>allowDupLedgerGDPdUFieldFieldNameIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the FieldNameIdx index in the LedgerGDPdUField table to allow for duplicate records.</p></td>
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
<td><p>LedgerGDPdUField</p></td>
</tr>
</tbody>
</table>


## Remarks

The GDPdUGroupId field is replaced with the new LedgerGDPdUTable surrogate key field in the unique FieldNameIdx index. Initially, this field contains no value. Therefore, the index is set to allow for duplicate values before the field is updated with the value of the RecId field of the LedgerGDPdUTable table.

  


