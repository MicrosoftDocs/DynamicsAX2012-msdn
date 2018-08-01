---
title: ReleaseUpdateDB60_Ledger.verifyUniqueLedgerEntryReference Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.verifyUniqueLedgerEntryReference Upgrade Script
ms:assetid: 9845f4cf-a7b2-05f7-c6bc-21bd63d75b8e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686238(v=AX.60)
ms:contentKeyID: 49709939
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.verifyUniqueLedgerEntryReference Upgrade Script 


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
<td><p>verifyUniqueLedgerEntryReference</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Makes sure that only unique values exist for the alternative key on the LedgerEntryReference table. The values are generated during the PreUpgrade process.</p></td>
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
<td><p>LedgerEntryReference</p></td>
</tr>
</tbody>
</table>

  


