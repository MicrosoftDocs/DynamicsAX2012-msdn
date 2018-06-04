---
title: ReleaseUpdateDB60_Ledger.updateTaxAuthorityAddress Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxAuthorityAddress Upgrade Script
ms:assetid: d250a5cf-ff0c-c4de-3fdb-4135113d6273
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686955(v=AX.60)
ms:contentKeyID: 49711405
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxAuthorityAddress Upgrade Script 


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
<td><p>updateTaxAuthorityAddress</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The AccountRoundOffGain and AccountRoundOffLoss fields need to be converted to the RoundOffGainLedgerDimension and RoundOffLossLedgerDimension due to the new accounts and dimension model changes.</p></td>
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
<td><p>TaxAuthorityAddress</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TaxAuthorityAddress</p></th>
<th><p>To Table: TaxAuthorityAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountRoundOffGain</p></td>
<td><p>RoundOffGainLedgerDimension</p></td>
</tr>
<tr class="even">
<td><p>AccountRoundOffLoss</p></td>
<td><p>RoundOffLossLedgerDimension</p></td>
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
<td><p>TaxAuthorityAddress</p></td>
<td><p>RoundOffGainLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>TaxAuthorityAddress</p></td>
<td><p>RoundOffLossLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
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
<td><p>TaxAuthorityAddress</p></td>
<td><p>AccountRoundOffGain</p></td>
</tr>
<tr class="even">
<td><p>TaxAuthorityAddress</p></td>
<td><p>AccountRoundOffLoss</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

