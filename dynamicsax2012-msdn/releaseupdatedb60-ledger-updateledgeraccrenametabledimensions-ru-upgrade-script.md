---
title: ReleaseUpdateDB60_Ledger.updateLedgerAccRenameTableDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerAccRenameTableDimensions_RU Upgrade Script
ms:assetid: dc9d8d1e-7bc2-a81c-64ce-446d61f9c5e8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737195(v=AX.60)
ms:contentKeyID: 49711638
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerAccRenameTableDimensions\_RU Upgrade Script [AX 2012]


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
<td><p>updateLedgerAccRenameTableDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the FromAccount, ToAccount, and TempAccount fields to the FromMainAccountId, ToMainAccountId, and TempMainAccountId fields respectively in the LedgerAccountCov table.</p></td>
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
<td><p>LedgerAccountRenameTable_RU</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerAccountRenameTable_RU</p></th>
<th><p>To Table: LedgerAccountRenameTable_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FromAccount</p></td>
<td><p>FromMainAccountId</p></td>
</tr>
<tr class="even">
<td><p>ToAccount</p></td>
<td><p>ToMainAccountId</p></td>
</tr>
<tr class="odd">
<td><p>TempAccount</p></td>
<td><p>TempMainAccountId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

