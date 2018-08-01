﻿---
title: ReleaseUpdateDB60_Ledger.allowNoDupLedgerClosingTableShMnAcctIdx Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupLedgerClosingTableShMnAcctIdx Upgrade Script
ms:assetid: 3aeda397-a99d-194d-7a66-e0e4a63f871f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685264(v=AX.60)
ms:contentKeyID: 49707717
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupLedgerClosingTableShMnAcctIdx Upgrade Script [AX 2012]


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
<td><p>allowNoDupLedgerClosingTableShMnAcctIdx</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ShMnAcctIdx index in the LedgerClosingTable table not to allow for duplicate records.</p></td>
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
<td><p>LedgerClosingTable</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the MainAccount surrogate key field with the value of the record ID field of the MainAccount table, the ShMnAcctIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

