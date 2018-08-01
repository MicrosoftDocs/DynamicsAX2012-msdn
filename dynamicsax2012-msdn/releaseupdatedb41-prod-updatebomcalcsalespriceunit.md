---
title: ReleaseUpdateDB41_Prod.updateBOMCalcSalesPriceUnit
TOCTitle: ReleaseUpdateDB41_Prod.updateBOMCalcSalesPriceUnit
ms:assetid: f3b30113-74e5-f5e0-4729-3689c264d841
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737491(v=AX.60)
ms:contentKeyID: 49712185
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Prod.updateBOMCalcSalesPriceUnit 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Prod</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBOMCalcSalesPriceUnit</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the BOMCalcTrans.SalesPriceUnit field.</p></td>
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
<td><p>Production</p></td>
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
<td><p>BOMCalcTrans</p></td>
</tr>
</tbody>
</table>


## Remarks

If the value of the BOMCalcTrans.SalesPriceUnit field is equal to zero, it is updated with the value of the BOMCalcTrans.CostPriceUnit field.

  


