---
title: ReleaseUpdateTransformDB40_Ledger.ledgerTableOffsetOpeningDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.ledgerTableOffsetOpeningDelta Upgrade Script
ms:assetid: 97664e10-03ab-e22a-adff-51742daef58f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686213(v=AX.60)
ms:contentKeyID: 49709916
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.ledgerTableOffsetOpeningDelta Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ledgerTableOffsetOpeningDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Converts the OffsetAccount and OpeningAccount fields in the LedgerTable to the dimensions fields in the MainAccount table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>MainAccount</p></td>
</tr>
<tr class="even">
<td><p>LedgerTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert the account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerTable</p></th>
<th><p>To Table: MainAccount</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>OffsetAccount</p></td>
<td><p>OffsetLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>OpeningAccount</p></td>
<td><p>OpeningAccount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

