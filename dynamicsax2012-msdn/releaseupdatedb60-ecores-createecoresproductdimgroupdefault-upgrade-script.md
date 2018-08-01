---
title: ReleaseUpdateDB60_EcoRes.createEcoResProductDimGroupDefault Upgrade Script
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResProductDimGroupDefault Upgrade Script
ms:assetid: 4f0d785c-5db8-750d-0e1c-4d7a05182238
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685478(v=AX.60)
ms:contentKeyID: 49708181
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResProductDimGroupDefault Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_EcoRes</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createEcoResProductDimGroupDefault</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates a new default record in the EcoResProductDimensionGroup table plus records for each dimension in the EcoResProductDimensionGroupFldSetup table.</p></td>
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
<td><p>Product management</p></td>
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
<td><p>EcoResProductDimensionGroup</p></td>
</tr>
<tr class="even">
<td><p>EcoResProductDimensionGroupFldSetup</p></td>
</tr>
</tbody>
</table>


## Remarks

This method handles the scenario where the license for \<c\>LogisticsAdvanced\</c\> did not exist in the source system being upgraded. In this version of Ax we merge the two licenses \<c\>LogisticsBasic\</c\> and \<c\>LogisticsAdvanced\</c\> and thereby makes dimensions group mandatory.

  


