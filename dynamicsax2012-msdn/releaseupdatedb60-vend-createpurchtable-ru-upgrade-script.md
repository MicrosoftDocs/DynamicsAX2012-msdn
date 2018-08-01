---
title: ReleaseUpdateDB60_Vend.createPurchTable_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createPurchTable_RU Upgrade Script
ms:assetid: 31c0e3cb-ef47-0391-e1fe-595713b7f0e9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736095(v=AX.60)
ms:contentKeyID: 49707509
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createPurchTable\_RU Upgrade Script 


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
<td><p>createPurchTable_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates Russia country specific fields from the &lt;c&gt;PurchTable&lt;/c&gt; table to &lt;c&gt;PurchTable_RU&lt;/c&gt; table</p></td>
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
<td><p>PurchTable</p></td>
</tr>
<tr class="even">
<td><p>PurchTable_RU</p></td>
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
<th><p>From Table: PurchTable</p></th>
<th><p>To Table: PurchTable_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AgreementHeaderExt_RU</p></td>
<td><p>AgreementHeaderExt_RU</p></td>
</tr>
<tr class="even">
<td><p>ConsigneeAccount_RU</p></td>
<td><p>ConsigneeAccount_RU</p></td>
</tr>
<tr class="odd">
<td><p>ConsignorAccount_RU</p></td>
<td><p>ConsignorAccount_RU</p></td>
</tr>
<tr class="even">
<td><p>EmplAccount_RU</p></td>
<td><p>EmplAccount_RU</p></td>
</tr>
<tr class="odd">
<td><p>InventProfileId_RU</p></td>
<td><p>InventProfileId_RU</p></td>
</tr>
<tr class="even">
<td><p>InventProfileType_RU</p></td>
<td><p>InventProfileType_RU</p></td>
</tr>
<tr class="odd">
<td><p>PriceAgreementDate_RU</p></td>
<td><p>PriceAgreementDate_RU</p></td>
</tr>
<tr class="even">
<td><p>VATChargeSource_RU</p></td>
<td><p>VATChargeSource_RU</p></td>
</tr>
<tr class="odd">
<td><p>VATOperationCode_RU</p></td>
<td><p>VATOperationCode_RU</p></td>
</tr>
</tbody>
</table>

  


