---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxLedgerAccountSetup_INLedger
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxLedgerAccountSetup_INLedger
ms:assetid: a002b46d-cdfa-7aa0-e1a9-40f637337dcb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736694(v=AX.60)
ms:contentKeyID: 49710126
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxLedgerAccountSetup\_INLedger [AX 2012]


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
<td><p>allowNoDupTaxLedgerAccountSetup_INLedger</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;GroupCodeNumIdx&lt;/c&gt; in the table &lt;c&gt;TaxLedgerAccountSetup_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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

After updating the surrogate key fields TaxLedgerAccountGroup and TaxRegistrationNumberTable with the value of the RecId field of the tables TaxLedgerAccountGroup\_IN and TaxRegistrationNumberTable\_IN, the index GroupCodeNumIdx is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

