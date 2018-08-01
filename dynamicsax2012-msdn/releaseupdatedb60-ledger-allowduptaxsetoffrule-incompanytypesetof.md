---
title: ReleaseUpdateDB60_Ledger.allowDupTaxSetOffRule_INCompanyTypeSetOf
TOCTitle: ReleaseUpdateDB60_Ledger.allowDupTaxSetOffRule_INCompanyTypeSetOf
ms:assetid: 00620947-8548-b463-07e2-fa976359be74
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684610(v=AX.60)
ms:contentKeyID: 49706307
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowDupTaxSetOffRule\_INCompanyTypeSetOf 


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
<td><p>allowDupTaxSetOffRule_INCompanyTypeSetOf</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the indexes &lt;c&gt;ComponentColumnIdx and ComponentTypeSetOffComponentTypeIdx&lt;/c&gt; in the table &lt;c&gt;TaxSetOffRule_IN&lt;/c&gt; to allow duplicate records.</p></td>
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
<td><p>TAXSETOFFRULE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

The Component field is replaced with the new surrogate key field TaxComponentTable in the unique index ComponentColumnIdx. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId field of the table TaxComponentTable\_IN. The Component field is replaced with the new surrogate key field TaxComponentTable and TaxComponentTableSetoff in the unique index ComponentColumnIdx and ComponentTypeSetOffComponentTypeIdx. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId field of the table TaxComponentTable\_IN.

  


