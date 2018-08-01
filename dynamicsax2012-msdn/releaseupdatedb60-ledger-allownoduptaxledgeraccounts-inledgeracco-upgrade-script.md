---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxLedgerAccounts_INLedgerAcco Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxLedgerAccounts_INLedgerAcco Upgrade Script
ms:assetid: b58f35b8-26b7-2af7-ce56-5b8299087f86
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737005(v=AX.60)
ms:contentKeyID: 49710687
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxLedgerAccounts\_INLedgerAcco Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>allowNoDupTaxLedgerAccounts_INLedgerAcco</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the GroupCodeNumTypeComponentIdx index in the TaxLedgerAccounts_IN table not to allow duplicate records.</p></td>
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
<td><p>TAXLEDGERACCOUNTS_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the TaxLedgerAccountSetup, TaxComponentTable, and LedgerDimension surrogate key fields with the value of the RecId field of the TaxLedgerAccountSetup\_IN, TaxComponentTable\_IN, and DimensionAttributeValueCombination tables. The GroupCodeNumTypeComponentIdx index is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

