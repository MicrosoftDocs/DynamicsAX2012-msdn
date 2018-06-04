---
title: ReleaseUpdateDB60_Invent.allowDupTaxInventVATCommodityCode_INItem Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.allowDupTaxInventVATCommodityCode_INItem Upgrade Script
ms:assetid: b2b79ab3-39ae-9f2f-d8a8-bd8ec3d79ac9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736913(v=AX.60)
ms:contentKeyID: 49710597
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowDupTaxInventVATCommodityCode\_INItem Upgrade Script 


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
<td><p>allowDupTaxInventVATCommodityCode_INItem</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the ItemLogisticAddressStateIdx index in the TaxInventVATCommodityCode_IN table to allow duplicate records.</p></td>
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

The StateId field is replaced with the new LogisticsAddressStateId global address field in the unique ItemLogisticAddressStateIdx index. Initially this field contains no value. So the index is set to allow duplicates before the field is updated with the value of the RecId field of the TaxInventVATCommodityCode\_IN table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

