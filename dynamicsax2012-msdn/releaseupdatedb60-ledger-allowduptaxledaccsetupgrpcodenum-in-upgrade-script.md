---
title: ReleaseUpdateDB60_Ledger.allowDupTaxLedAccSetupGrpCodeNum_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxLedAccSetupGrpCodeNum_IN Upgrade Script
ms:assetid: 2057d08d-a3e0-e69e-e002-fb98a5d9c288
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684885(v=AX.60)
ms:contentKeyID: 49707088
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxLedAccSetupGrpCodeNum\_IN Upgrade Script [AX 2012]


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
<td><p>TaxLedgerAccountSetup_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxAccountGroup and RegistrationNumber fields are replaced with the new TaxLedgerAccountGroup and TaxRegistrationNumberTable surrogate key field in the GroupCodeNumIdx unique index. Initially these fields contains no value. So the index is set to allow for duplicates before the field is updated with the value of the record ID fields in the TaxLedgerAccountGroup\_IN and TaxRegistrationNumberTable\_IN tables.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

