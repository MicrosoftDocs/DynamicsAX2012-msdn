---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxLedAccGrpCodeNumCompIdx_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxLedAccGrpCodeNumCompIdx_IN Upgrade Script
ms:assetid: bba3d31a-7353-df0a-5788-4be67d7d565e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686639(v=AX.60)
ms:contentKeyID: 49710847
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxLedAccGrpCodeNumCompIdx\_IN Upgrade Script 


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
<td><p>allowNoDupTaxLedAccGrpCodeNumCompIdx_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the GroupCodeNumTypeComponentIdx index in the TaxLedgerAccounts_IN table not to allow for duplicate records.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>TaxLedgerAccounts_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the TaxLedgerAccountSetup, TaxComponentTable and LedgerDimension surrogate key fields with the value of the record ID field in the TaxLedgerAccountSetup\_IN, TaxComponentTable\_IN, and DimensionAttributeValueCombination tables, the GroupCodeNumTypeComponentIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

