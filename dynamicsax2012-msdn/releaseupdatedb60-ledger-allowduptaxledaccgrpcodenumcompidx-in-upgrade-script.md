---
title: ReleaseUpdateDB60_Ledger.allowDupTaxLedAccGrpCodeNumCompIdx_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxLedAccGrpCodeNumCompIdx_IN Upgrade Script
ms:assetid: 346ef048-6c6c-3b68-1339-625a5d592542
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685128(v=AX.60)
ms:contentKeyID: 49707581
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxLedAccGrpCodeNumCompIdx\_IN Upgrade Script 


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
<td><p>allowDupTaxLedAccGrpCodeNumCompIdx_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the GroupCodeNumTypeComponentIdx index in the TaxLedgerAccounts_IN table to allow for duplicate records.</p></td>
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

The TaxAccountGroup, AccountCode and RegistrationNumber fields are replaced with the new TaxLedgerAccountSetup surrogate key field in the GroupCodeNumTypeComponentIdx unique index. Also, the Component and LedgerAccount fields are replaced with the record IDs of the TaxComponentTable\_IN and DimensionAttributeValueComibation tables. Initially these fields contains no values. So the index is set to allow for duplicates before the field is updated with the value of the record IDs of the corresponding tables.

  


