---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximEntitlementDetails_INSchem
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximEntitlementDetails_INSchem
ms:assetid: 9426144a-2864-8843-5101-fc648193e461
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686139(v=AX.60)
ms:contentKeyID: 49709843
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximEntitlementDetails\_INSchem 


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
<td><p>Updates the index &lt;c&gt;SchemeLineProductGroupIdx&lt;/c&gt; in the table &lt;c&gt;EximEntitlementDetails_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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

After updating the surrogate key field EximProductGroupTable RecId field of the table, the index SchemeTableProductGroupIdx is reset not to allow duplicate records.

  


