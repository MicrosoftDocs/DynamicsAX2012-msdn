---
title: ReleaseUpdateDB41_Prod.updateBOMCalcSalesPriceUnit Upgrade Script
TOCTitle: ReleaseUpdateDB41_Prod.updateBOMCalcSalesPriceUnit Upgrade Script
ms:assetid: 7a9b5b34-1acf-0b81-48c7-0b98cbcc531e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719431(v=AX.60)
ms:contentKeyID: 49709222
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Prod.updateBOMCalcSalesPriceUnit Upgrade Script 


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

If the SalesPriceUnit field is equal to zero, it is updated with the CostPriceUnit value.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

