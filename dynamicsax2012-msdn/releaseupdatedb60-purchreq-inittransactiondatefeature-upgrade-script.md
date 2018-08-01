---
title: ReleaseUpdateDB60_PurchReq.initTransactionDateFeature Upgrade Script
TOCTitle: ReleaseUpdateDB60_PurchReq.initTransactionDateFeature Upgrade Script
ms:assetid: 986e81b3-ad19-db11-2816-8eda88d5a268
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686242(v=AX.60)
ms:contentKeyID: 49709945
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PurchReq.initTransactionDateFeature Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_PurchReq</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initTransactionDateFeature</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The TransDate field on the PurchReqTable and PurchReqLine records is being set to required date. The transaction date is also set to the default value from the requirement date on the PurchReqParameters table.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>PurchReqParameters</p></td>
</tr>
<tr class="even">
<td><p>PurchReqTable</p></td>
</tr>
<tr class="odd">
<td><p>PurchReqLine</p></td>
</tr>
</tbody>
</table>

  


