---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximDEPBDetailsTable_INSchemes Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximDEPBDetailsTable_INSchemes Upgrade Script
ms:assetid: 6617247c-bfa6-45f3-58f2-39b32abda560
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719218(v=AX.60)
ms:contentKeyID: 49708757
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximDEPBDetailsTable\_INSchemes Upgrade Script 


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
<td><p>allowNoDupEximDEPBDetailsTable_INSchemes</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SchemesTableProductGroupIdx index in the EximDEPBDetailsTable_IN table to not allow duplicate records.</p></td>
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
<td><p>EXIMDEPBDETAILSTABLE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key field in the EximProductGroupTable table, the SchemesTableProductGroupIdx index is reset to not allow duplicate records.

  


