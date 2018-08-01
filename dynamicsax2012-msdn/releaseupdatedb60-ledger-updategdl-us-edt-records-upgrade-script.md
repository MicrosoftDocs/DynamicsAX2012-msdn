---
title: ReleaseUpdateDB60_Ledger.updateGDL_US_EDT_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_US_EDT_Records Upgrade Script
ms:assetid: d5df30d0-7c76-b97b-da1a-fddb4f210afc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687031(v=AX.60)
ms:contentKeyID: 49711480
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_US\_EDT\_Records Upgrade Script 


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
<td><p>updateGDL_US_EDT_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the surrogate key column in the foreign tables with the value from the RecId field of the primary table.</p></td>
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
<td><p>LedgerJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>Tax1099Fields</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the Tax1099Fields field in the LedgerJournalTrans table with the value from the RecId field of the Tax1099Fields table.

  


