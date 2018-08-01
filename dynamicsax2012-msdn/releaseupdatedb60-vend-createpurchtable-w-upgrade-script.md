---
title: ReleaseUpdateDB60_Vend.createPurchTable_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createPurchTable_W Upgrade Script
ms:assetid: 4a4b3244-eef9-688c-fbde-254ef856d369
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685375(v=AX.60)
ms:contentKeyID: 49708102
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createPurchTable\_W Upgrade Script 


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
<td><p>createPurchTable_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country specific fields from the &lt;c&gt;PurchTable&lt;/c&gt; table to &lt;c&gt;PurchTable_W&lt;/c&gt; table</p></td>
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
<td><p>PurchTable_W</p></td>
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
<th><p>To Table: PurchTable_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomsImportOrder_IN</p></td>
<td><p>CustomsImportOrder_IN</p></td>
</tr>
<tr class="even">
<td><p>CustomsInvoiceRegistered_IN</p></td>
<td><p>CustomsInvoiceRegistered_IN</p></td>
</tr>
<tr class="odd">
<td><p>NatureOfAssessee_IN</p></td>
<td><p>NatureOfAssessee_IN</p></td>
</tr>
<tr class="even">
<td><p>TCSGroup_IN</p></td>
<td><p>TCSGroup_IN</p></td>
</tr>
<tr class="odd">
<td><p>TDSGroup_IN</p></td>
<td><p>TDSGroup_IN</p></td>
</tr>
</tbody>
</table>

  


