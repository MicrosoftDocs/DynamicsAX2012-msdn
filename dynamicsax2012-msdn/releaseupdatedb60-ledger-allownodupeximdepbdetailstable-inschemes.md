---
title: ReleaseUpdateDB60_Ledger.allowNoDupEximDEPBDetailsTable_INSchemes
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupEximDEPBDetailsTable_INSchemes
ms:assetid: 1d5734c4-6666-2cc0-6b93-87d89a62dacc
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684810(v=AX.60)
ms:contentKeyID: 49707013
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupEximDEPBDetailsTable\_INSchemes [AX 2012]


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
<td><p>Updates the index &lt;c&gt;SchemesTableProductGroupIdx&lt;/c&gt; in the table &lt;c&gt;EximDEPBDetailsTable_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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

After updating the surrogate key field EximProductGroupTable, the index SchemesTableProductGroupIdx is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

