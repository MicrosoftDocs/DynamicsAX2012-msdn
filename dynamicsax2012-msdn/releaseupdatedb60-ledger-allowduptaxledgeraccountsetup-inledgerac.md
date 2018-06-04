---
title: ReleaseUpdateDB60_Ledger.allowDupTaxLedgerAccountSetup_INLedgerAc
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxLedgerAccountSetup_INLedgerAc
ms:assetid: 4d82fed1-4a8c-e71e-2142-b4f36b85e4e4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685441(v=AX.60)
ms:contentKeyID: 49708146
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxLedgerAccountSetup\_INLedgerAc 


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
<td><p>allowDupTaxLedgerAccountSetup_INLedgerAc</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;GroupCodeNumIdx&lt;/c&gt; in the table &lt;c&gt;TaxLedgerAccountSetup_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>TAXLEDGERACCOUNTSETUP_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxAccountGroup and RegistrationNumber fields are replaced with the new surrogate key field TaxLedgerAccountGroup and TaxRegistrationNumberTable in the unique index GroupCodeNumIdx. Initially these fields contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId fields of the table TaxLedgerAccountGroup\_IN and TaxRegistrationNumberTable\_IN tables.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

