---
title: ReleaseUpdateDB60_Invent.allowNoDupTaxInventVATCommodityCode_INIt Upgrade Script
TOCTitle: ReleaseUpdateDB60_Invent.allowNoDupTaxInventVATCommodityCode_INIt Upgrade Script
ms:assetid: d251bada-81c9-c90b-e4dd-d5be65e160b8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686980(v=AX.60)
ms:contentKeyID: 49711430
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Invent.allowNoDupTaxInventVATCommodityCode\_INIt Upgrade Script 


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
<td><p>Updates the ItemLogisticAddressStateIdx index in the TaxInventVATCommodityCode_IN table not to allow duplicate records.</p></td>
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

Truncated method name from the allowNoDupItemLogisticAddressStateIdx index. After updating the LogisticsAddressStateId field in the TaxInventVATCommodityCode\_IN table with the value of the NewStateId field of the del\_AddressStateUpgrade table, the ItemLogisticAddressStateIdx index is reset not to allow duplicate records.

  


