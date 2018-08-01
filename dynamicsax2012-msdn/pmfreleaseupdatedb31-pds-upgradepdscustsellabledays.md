---
title: PmfReleaseUpdateDB31_Pds.upgradePdsCustSellableDays
TOCTitle: PmfReleaseUpdateDB31_Pds.upgradePdsCustSellableDays
ms:assetid: 70784b6a-f1cb-3bab-edd7-8a381b7c9a0f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685784(v=AX.60)
ms:contentKeyID: 49708983
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# PmfReleaseUpdateDB31\_Pds.upgradePdsCustSellableDays 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>PmfReleaseUpdateDB31_Pds</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>upgradePdsCustSellableDays</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the PdsCustSellableDays table with the customer reference and the related del_PdsSellableDays value.</p></td>
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
<td><p>Process Distribution</p></td>
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
<td><p>CustTable</p></td>
</tr>
<tr class="even">
<td><p>PdsCustSellableDays</p></td>
</tr>
</tbody>
</table>


## Remarks

The method will find any CustTable records that currently have a del\_PdsSellableDays value. For each record, an entry will be created in the PdsCustSellableDays table and the value of the PdsSellableDays field from the CustTable table will be entered as a PdsSellableDays value in the new table. Then a validation will be conducted to verify that the correct value was entered for the customer and the customer record and the PdsSellableDays field value will be set to zero and the CustTable record is updated.

  


