---
title: ReleaseUpdateDB60_Ledger.allowNoDupTaxLedAccSetupGrpCodeNum_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupTaxLedAccSetupGrpCodeNum_IN Upgrade Script
ms:assetid: c7d74e55-27db-2339-293a-af86946134cc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719576(v=AX.60)
ms:contentKeyID: 49711143
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupTaxLedAccSetupGrpCodeNum\_IN Upgrade Script 


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
<td><p>allowNoDupTaxLedAccSetupGrpCodeNum_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the GroupCodeNumIdx index in the TaxLedgerAccountSetup_IN table not to allow for duplicate records.</p></td>
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

After updating the TaxLedgerAccountGroup and TaxRegistrationNumberTable surrogate key fields with the value of the record ID field in the TaxLedgerAccountGroup\_IN and TaxRegistrationNumberTable\_IN tables, the GroupCodeNumIdx index is reset not to allow for duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

