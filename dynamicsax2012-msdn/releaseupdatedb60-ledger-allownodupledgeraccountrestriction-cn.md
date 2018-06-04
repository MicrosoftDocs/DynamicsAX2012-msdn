---
title: ReleaseUpdateDB60_Ledger.allowNoDupLedgerAccountRestriction_CN
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupLedgerAccountRestriction_CN
ms:assetid: 93e9c53a-b66b-8147-f705-4f8597b11969
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686131(v=AX.60)
ms:contentKeyID: 49709834
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupLedgerAccountRestriction\_CN 


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
<td><p>allowNoDupLedgerAccountRestriction_CN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the AccountRestrictionIdx index in the LedgerAccountRestriction_CN table not to allow for duplicate records.</p></td>
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
<td><p>LedgerAccountRestriction_CN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the LedgerAccountRestriction\_CN surrogate key field with the value of the RecId field of the LedgerAccountRestriction\_CN table, the AccountRestrictionIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

