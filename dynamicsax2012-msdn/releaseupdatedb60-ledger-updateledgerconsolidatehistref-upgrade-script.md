---
title: ReleaseUpdateDB60_Ledger.updateLedgerConsolidateHistRef Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerConsolidateHistRef Upgrade Script
ms:assetid: d30c5128-8ebc-0103-ba3b-da7e30c56a41
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686992(v=AX.60)
ms:contentKeyID: 49711441
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerConsolidateHistRef Upgrade Script [AX 2012]


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
<td><p>updateLedgerConsolidateHistRef</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Removes the LedgerConsolidateHistRef records that are associated to ledger budget data.</p></td>
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
<td><p>LedgerConsolidateHistRef</p></td>
</tr>
</tbody>
</table>


## Remarks

This method removes all records in the LedgerConsolidateHistRef table that are associated to ledger budget data. These records have the TransTableId field set to the LedgerBudget table ID. This method is to be run as a PostSync, Standard job.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

