---
title: ReleaseUpdateDB60_Ledger.allowDupTaxLedgerAccounts_INLedgerAccoun
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxLedgerAccounts_INLedgerAccoun
ms:assetid: b25852dd-d401-a01b-6789-ae9137ac4c9a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736924(v=AX.60)
ms:contentKeyID: 49710608
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxLedgerAccounts\_INLedgerAccoun 


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
<td><p>allowDupTaxLedgerAccounts_INLedgerAccoun</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;GroupCodeNumTypeComponentIdx&lt;/c&gt; in the table &lt;c&gt;TaxLedgerAccounts_IN&lt;/c&gt; to allow duplicate records.</p></td>
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

The TaxAccountGroup, AccountCode and RegistrationNumber fields are replaced with the new surrogate key field TaxLedgerAccountSetup in the unique index GroupCodeNumTypeComponentIdx. Also, the Component and LedgerAccount fields are replaced with the Rec Ids of TaxComponentTable\_IN and DimensionAttributeValueComibation tables. Initially these fields contains no values. So the index is set to allow duplicates before the field is updated with the value of the RecId's of the corresponding tables.

  


