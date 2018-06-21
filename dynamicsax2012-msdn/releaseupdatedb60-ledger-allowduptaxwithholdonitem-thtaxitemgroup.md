---
title: ReleaseUpdateDB60_Ledger.allowDupTaxWithholdOnItem_THTaxItemGroup
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxWithholdOnItem_THTaxItemGroup
ms:assetid: 0d7c8512-3f4d-857d-70e8-48134bd0bef3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735714(v=AX.60)
ms:contentKeyID: 49706620
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxWithholdOnItem\_THTaxItemGroup [AX 2012]


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
<td><p>allowDupTaxWithholdOnItem_THTaxItemGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;TaxItemGroupIdx&lt;/c&gt; in the table &lt;c&gt;TaxWithholdOnItem_TH&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>TaxWithholdOnItem_TH</p></td>
</tr>
</tbody>
</table>


## Remarks

The TaxWithholdItemGroup field is replaced with the new surrogate key field TaxWithholdItemGroupHeading\_TH in the unique index TaxItemGroupIdx. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId field of the table TaxWithholdItemGroupHeading\_TH.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

