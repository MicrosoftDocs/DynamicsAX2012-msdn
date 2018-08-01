﻿---
title: ReleaseUpdateTransformDB50_Prod.ProdIndirectTransDeltaPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Prod.ProdIndirectTransDeltaPreUpgradeProcess Upgrade Script
ms:assetid: 437a2dc6-5fe6-0f68-be32-57f48a5cebed
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718874(v=AX.60)
ms:contentKeyID: 49707918
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Prod.ProdIndirectTransDeltaPreUpgradeProcess Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ProdIndirectTransDeltaPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Dimension, AccountIndirectAbsorption, and AccountIndirectAbsorptionOffset fields of the prodIndirectTrans table to the defaultDimension, IndirectAbsorptionLedgerDimension, and IndirectAbsorptionOffsetLedgerDimension fields of the shadow_prodIndirectTrans table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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
<td><p>Manufacture</p></td>
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
<td><p>ProdIndirectTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to convert the account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProdIndirectTrans</p></th>
<th><p>To Table: ProdIndirectTrans</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountIndirectAbsorption</p></td>
<td><p>IndirectAbsorptionLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AccountIndirectAbsorptionOffset</p></td>
<td><p>IndirectAbsorptionOffsetLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>AccountWIPIssue</p></td>
<td><p>EstimatedIndirectAbsorpLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AccountWIPValuation</p></td>
<td><p>EstimIndirectAbsorpOffsetLedgerDimension</p></td>
</tr>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
</tbody>
</table>


## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ProdIndirectTrans</p></td>
<td><p>IndirectAbsorptionLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="even">
<td><p>ProdIndirectTrans</p></td>
<td><p>IndirectAbsorptionOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="odd">
<td><p>ProdIndirectTrans</p></td>
<td><p>EstimatedIndirectAbsorpLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="even">
<td><p>ProdIndirectTrans</p></td>
<td><p>EstimIndirectAbsorpOffsetLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="odd">
<td><p>ProdIndirectTrans</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ProdIndirectTrans</p></td>
<td><p>AccountIndirectAbsorption</p></td>
</tr>
<tr class="even">
<td><p>ProdIndirectTrans</p></td>
<td><p>AccountIndirectAbsorptionOffset</p></td>
</tr>
<tr class="odd">
<td><p>ProdIndirectTrans</p></td>
<td><p>AccountWIPIssue</p></td>
</tr>
<tr class="even">
<td><p>ProdIndirectTrans</p></td>
<td><p>AccountWIPValuation</p></td>
</tr>
<tr class="odd">
<td><p>ProdIndirectTrans</p></td>
<td><p>Dimension</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

