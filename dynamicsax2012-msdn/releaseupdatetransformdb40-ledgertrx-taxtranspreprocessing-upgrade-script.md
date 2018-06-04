---
title: ReleaseUpdateTransformDB40_LedgerTrx.taxTransPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_LedgerTrx.taxTransPreProcessing Upgrade Script
ms:assetid: 1c09693b-047a-3274-f49f-35d5f26eabc8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718694(v=AX.60)
ms:contentKeyID: 49706977
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_LedgerTrx.taxTransPreProcessing Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_LedgerTrx</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>taxTransPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Handles the live pre-processing of records in the TaxTrans table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
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
<td><p>TaxTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

Each of the TaxTrans records will be normalized into a new TaxTransGeneralJournalAccountEntry linking table. This is done for each record that has a value for the AccountNum, OperationAccount and TaxOffsetAccountUseTax fields.

This is a sergeant method which calls the other associated methods to perform this normalization against each record in the TaxTrans table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

