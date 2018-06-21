---
title: ReleaseUpdateTransformDB40_Ledger.taxTransDeltaPreProcessing Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.taxTransDeltaPreProcessing Upgrade Script
ms:assetid: a705f861-f777-58c9-fa7d-3f9fb6d1c798
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736871(v=AX.60)
ms:contentKeyID: 49710302
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.taxTransDeltaPreProcessing Upgrade Script [AX 2012]


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
<td><p>taxTransDeltaPreProcessing</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates and calls the stored procedures for the transformation of the TaxTrans table to the TaxTransLedgerEntry table for four different account types for any changes from the upgrade.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p>
<p>Preprocessing 60: Single user</p></td>
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
<tr class="even">
<td><p>TaxTransLedgerEntry</p></td>
</tr>
</tbody>
</table>


## Remarks

This methods calls various other methods that perform the actual transformations. The TaxTrans records are written to the TaxTransLedgerEntry table for the AccountNum, TaxOffsetAccount, OperationAccount and ChargeAccount.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TaxTrans</p></th>
<th><p>To Table: TaxTransLedgerEntry</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecID</p></td>
<td><p>TaxTrans</p></td>
</tr>
<tr class="even">
<td><p>(GeneratedValue)</p></td>
<td><p>TaxTransRelationshipType</p></td>
</tr>
<tr class="odd">
<td><p>(GeneratedValue)</p></td>
<td><p>LedgerEntry</p></td>
</tr>
<tr class="even">
<td><p>(GeneratedValue)</p></td>
<td><p>LedgerDimension</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

