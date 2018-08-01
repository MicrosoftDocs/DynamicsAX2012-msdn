---
title: ReleaseUpdateDB60_Invent.allowNoDupTaxInventVATCommodityCode_INIt
TOCTitle: ReleaseUpdateDB60_Invent.allowNoDupTaxInventVATCommodityCode_INIt
ms:assetid: 5696c704-0a04-daf4-237a-5cbc848d7ad5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736189(v=AX.60)
ms:contentKeyID: 49708364
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowNoDupTaxInventVATCommodityCode\_INIt 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Invent</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupTaxInventVATCommodityCode_INIt</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the index &lt;c&gt;ItemLogisticAddressStateIdx&lt;/c&gt; in the table &lt;c&gt;TaxInventVATCommodityCode_IN&lt;/c&gt; not to allow duplicate records.</p></td>
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
<td><p>Inventory management</p></td>
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
<td><p>TAXINVENTVATCOMMODITYCODE_IN</p></td>
</tr>
</tbody>
</table>


## Remarks

Truncated method name from allowNoDupItemLogisticAddressStateIdx. After updating the field LogisticsAddressStateId in TaxInventVATCommodityCode\_IN with the value of the NewStateId field of the table del\_AddressStateUpgrade, the index ItemLogisticAddressStateIdx is reset not to allow duplicate records.

  


