---
title: ReleaseUpdateDB60_Ledger.updateLedgerRelatedAccounts_ES Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerRelatedAccounts_ES Upgrade Script
ms:assetid: 448d1bd3-bdc9-c1ad-d0b7-8f3e0f1283eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718905(v=AX.60)
ms:contentKeyID: 49707936
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerRelatedAccounts\_ES Upgrade Script [AX 2012]


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
<td><p>updateLedgerRelatedAccounts_ES</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the FromAccountRecId and ToAccountRecId fields in the LedgerRelatedAccounts_ES table with references to the del_FromAccount and del_ToAccount fields in the LedgerRelatedAccounts_ES table.</p></td>
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
<td><p>LedgerRelatedAccounts_ES</p></td>
</tr>
</tbody>
</table>


## Remarks

FromAccount/ToAccount fields are replaced with the new fields FromAccountRecId/ToAccountRecId

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

