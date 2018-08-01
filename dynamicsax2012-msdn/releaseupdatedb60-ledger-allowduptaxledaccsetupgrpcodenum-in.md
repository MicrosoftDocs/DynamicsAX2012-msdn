---
title: ReleaseUpdateDB60_Ledger.allowDupTaxLedAccSetupGrpCodeNum_IN
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxLedAccSetupGrpCodeNum_IN
ms:assetid: 27afbd40-d93c-b72d-d3d2-fdd9f6cac1b4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735851(v=AX.60)
ms:contentKeyID: 49707269
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxLedAccSetupGrpCodeNum\_IN 


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
<td><p>allowDupTaxLedAccSetupGrpCodeNum_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the GroupCodeNumIdx index in the TaxLedgerAccountSetup_IN table to allow for duplicate records.</p></td>
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
<td><p>TaxLedgerAccountSetup_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxAccountGroup and RegistrationNumber fields are replaced with the new TaxLedgerAccountGroup and TaxRegistrationNumberTable surrogate key field in the GroupCodeNumIdx unique index. Initially these fields contain no value. So the index is set to allow for duplicates before the field is updated with the value of the record ID fields of the TaxLedgerAccountGroup\_IN and TaxRegistrationNumberTable\_IN tables.

  


