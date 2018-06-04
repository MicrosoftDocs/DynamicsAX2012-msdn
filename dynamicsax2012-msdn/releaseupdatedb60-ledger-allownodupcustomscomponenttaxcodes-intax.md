---
title: ReleaseUpdateDB60_Ledger.allowNoDupCustomsComponentTaxCodes_INTax
TOCTitle: ReleaseUpdateDB60_Ledger.allowNoDupCustomsComponentTaxCodes_INTax
ms:assetid: 6b95c85d-baf4-44b1-df78-00c69c4b86ef
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685676(v=AX.60)
ms:contentKeyID: 49708877
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.allowNoDupCustomsComponentTaxCodes\_INTax 


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
<td><p>allowNoDupCustomsComponentTaxCodes_INTax</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;TaxComponentTaxCodeIdx&lt;/c&gt; in the table &lt;c&gt;CustomsComponentTaxCodes_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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
<td><p>CUSTOMSCOMPONENTTAXCODES_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

After updating the surrogate key field TaxComponentTable with the value of the RecId field of the table, the index TaxComponentTaxCodeIdx is reset not to allow duplicate records.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

