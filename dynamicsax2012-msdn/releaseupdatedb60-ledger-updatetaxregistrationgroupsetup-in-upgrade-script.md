---
title: ReleaseUpdateDB60_Ledger.updateTaxRegistrationGroupSetup_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateTaxRegistrationGroupSetup_IN Upgrade Script
ms:assetid: 2228b1ab-7e27-f739-3642-2cfd602af66e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684940(v=AX.60)
ms:contentKeyID: 49707142
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateTaxRegistrationGroupSetup\_IN Upgrade Script [AX 2012]


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
<td><p>updateTaxRegistrationGroupSetup_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the TaxRegistrationNumberTable and TaxRegistrationGroupName fields in the TaxRegistrationGroupSetup_IN table with the corresponding value from the RecId field in the TaxRegistrationNumberTable_IN and TaxRegistrationGroup_IN tables respectively.</p></td>
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
<td><p>TaxRegistrationGroup_IN</p></td>
</tr>
<tr class="even">
<td><p>TaxRegistrationGroupSetup_IN</p></td>
</tr>
<tr class="odd">
<td><p>TaxRegistrationNumberTable_IN</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

