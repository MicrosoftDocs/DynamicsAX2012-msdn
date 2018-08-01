---
title: ReleaseUpdateTransformDB50_Ledger.ledgerTransDeltaGeneralJournalAccEntry Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Ledger.ledgerTransDeltaGeneralJournalAccEntry Upgrade Script
ms:assetid: d845e181-fa0f-5bd6-d4df-a4a791cb315e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687092(v=AX.60)
ms:contentKeyID: 49711540
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Ledger.ledgerTransDeltaGeneralJournalAccEntry Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerTransDeltaGeneralJournalAccEntry</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates the stored procedure that will write the LedgerTrans records to the GeneralJournalAccountEntry table from the last upgrade.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p>
<p>Preprocessing 60: Single user</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>LedgerTrans</p></td>
</tr>
<tr class="even">
<td><p>GeneralJournalAccountEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

No table transformations occur in this method.

  


