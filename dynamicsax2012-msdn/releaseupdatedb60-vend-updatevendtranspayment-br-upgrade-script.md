---
title: ReleaseUpdateDB60_Vend.updateVendTransPayment_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendTransPayment_BR Upgrade Script
ms:assetid: 9cf6fb6e-81ad-f596-1a0a-d79d35af9a8d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736616(v=AX.60)
ms:contentKeyID: 49710058
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendTransPayment\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateVendTransPayment_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the EPPaymentType_BR and EPPaymentWay_BR fields from the VendTrans table to the VendTransPayment_BR table.</p></td>
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
<td><p>Accounts payable</p></td>
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
<td><p>VendTransPayment_BR</p></td>
</tr>
</tbody>
</table>


## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendTrans</p></th>
<th><p>To Table: VendTransPayment_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>VendTrans</p></td>
</tr>
<tr class="even">
<td><p>DEL_PaymentType_BR</p></td>
<td><p>EPPaymentType_BR</p></td>
</tr>
<tr class="odd">
<td><p>DEL_PaymentWay_BR</p></td>
<td><p>EPPaymentWay_BR</p></td>
</tr>
</tbody>
</table>

  


