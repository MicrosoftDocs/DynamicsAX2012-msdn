---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximEntitlementDetails_INSchem Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximEntitlementDetails_INSchem Upgrade Script
ms:assetid: b4b455f3-e0e7-aea2-d79d-9604be6819ad
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736982(v=AX.60)
ms:contentKeyID: 49710666
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximEntitlementDetails\_INSchem Upgrade Script 


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
<td><p>allowNoDupEximEntitlementDetails_INSchem</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the SchemeLineProductGroupIdx index in the EximEntitlementDetails_IN table not to allow duplicate records.</p></td>
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
<td><p>EXIMENTITLEMENTDETAILS_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the EximProductGroupTable surrogate key field to the RecId field of the table, the SchemeTableProductGroupIdx index is reset to not allow duplicate records.

  


