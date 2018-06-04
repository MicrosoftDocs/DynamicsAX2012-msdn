---
title: ReleaseUpdateDB60_Vend.copyPurchLineAsset Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.copyPurchLineAsset Upgrade Script
ms:assetid: e34907cd-bca2-80cf-de39-56e1181ca551
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737347(v=AX.60)
ms:contentKeyID: 49711788
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.copyPurchLineAsset Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>copyPurchLineAsset</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the PurchParmLine_Asset table, which is related to the non-duplicate PurchParmLine table, to the VendInvoiceInfoLine_Asset table.</p></td>
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
<td><p>PurchParmLine</p></td>
</tr>
<tr class="even">
<td><p>PurchParmLine_Asset</p></td>
</tr>
<tr class="odd">
<td><p>PurchParmTable</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceInfoLine</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceInfoLine_Asset</p></td>
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
<th><p>From Table: PurchParmLine_Asset</p></th>
<th><p>To Table: VendInvoiceInfoLine_Asset</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CreateFixedAsset</p></td>
<td><p>CreateFixedAsset</p></td>
</tr>
<tr class="even">
<td><p>AssetGroup</p></td>
<td><p>AssetGroup</p></td>
</tr>
<tr class="odd">
<td><p>AssetId</p></td>
<td><p>AssetId</p></td>
</tr>
<tr class="even">
<td><p>AssetTransTypePurch</p></td>
<td><p>AssetTransTypePurch</p></td>
</tr>
<tr class="odd">
<td><p>AssetBookId</p></td>
<td><p>AssetBookId</p></td>
</tr>
<tr class="even">
<td><p>AssetAcquired</p></td>
<td><p>AssetAcquired</p></td>
</tr>
<tr class="odd">
<td><p>PurchParmLineRecId</p></td>
<td><p>VendInvoiceInfoLineRecId</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendInvoiceInfoLine</p></th>
<th><p>To Table: VendInvoiceInfoLine_Asset</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VendInvoiceInfoLine_Asset</p></td>
<td><p>VendInvoiceInfoLineRecId</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

