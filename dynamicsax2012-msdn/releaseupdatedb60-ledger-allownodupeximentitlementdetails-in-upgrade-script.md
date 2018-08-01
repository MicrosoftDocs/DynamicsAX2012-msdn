---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximEntitlementDetails_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximEntitlementDetails_IN Upgrade Script
ms:assetid: 7a5974b6-b8fd-625a-2890-7add5ac40410
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719424(v=AX.60)
ms:contentKeyID: 49709215
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximEntitlementDetails\_IN Upgrade Script 


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
<td><p>allowNoDupEximEntitlementDetails_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SchemeLineProductGroupIdx index in the EximEntitlementDetails_IN table not to allow for duplicate records.</p></td>
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
<td><p>EximEntitlementDetails_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key field EximProductGroupTable RecId field of the table, the index SchemeTableProductGroupIdx is reset not to allow duplicate records.

  


