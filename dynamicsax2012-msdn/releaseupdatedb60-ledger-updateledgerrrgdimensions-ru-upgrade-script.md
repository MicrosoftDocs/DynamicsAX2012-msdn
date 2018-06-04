---
title: ReleaseUpdateDB60_Ledger.updateLedgerRRGDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerRRGDimensions_RU Upgrade Script
ms:assetid: 11d73bed-570e-acf2-68fd-37ac714d8665
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735813(v=AX.60)
ms:contentKeyID: 49706723
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerRRGDimensions\_RU Upgrade Script 


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
<td><p>updateLedgerRRGDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the Account field to the LedgerDimension field in the TaxReportLedgerAccounts table.</p></td>
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
<td><p>LedgerRRGAccountInterval_RU</p></td>
</tr>
<tr class="even">
<td><p>LedgerRRGOffsetAccountInterval_RU</p></td>
</tr>
<tr class="odd">
<td><p>LedgerRRGTax25ProfitInterval_RU</p></td>
</tr>
<tr class="even">
<td><p>LedgerRRGDimensionInterval_RU</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

