---
title: ReleaseUpdateDB60_Vend.updateVendPurchOrderJour Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendPurchOrderJour Upgrade Script
ms:assetid: c8fdbde8-3dec-bd19-72b6-955988bac252
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719606(v=AX.60)
ms:contentKeyID: 49711173
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendPurchOrderJour Upgrade Script [AX 2012]


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
<td><p>updateVendPurchOrderJour</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Finishes the processing of the staging tables that were populated in the pre-processing process. Re-creates the deleted purchase orders, including lines and miscellaneous charges. Splits the purchase order journal if the summery was updated in the previous version.</p></td>
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
<td><p>VendPurchOrderJour</p></td>
</tr>
<tr class="even">
<td><p>PurchTable</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
</tr>
<tr class="even">
<td><p>MarkupTrans</p></td>
</tr>
<tr class="odd">
<td><p>PurchTableDelete</p></td>
</tr>
<tr class="even">
<td><p>PurchLineDelete</p></td>
</tr>
<tr class="odd">
<td><p>PurchTableHistory</p></td>
</tr>
<tr class="even">
<td><p>PurchLineHistory</p></td>
</tr>
<tr class="odd">
<td><p>MarkupTransHistory</p></td>
</tr>
<tr class="even">
<td><p>DEL_VendPurchOrderJourSplit</p></td>
</tr>
<tr class="odd">
<td><p>DEL_VendPurchOrderDelete</p></td>
</tr>
</tbody>
</table>


## Remarks

In the pre-processing process, the new history tables were populated. However, any change to the original tables is postponed until the post-processing process. Summery updates of purchase order posting, that is the confirmation, is no longer allowed, and summery updates that were processed in the previous version are split into individual journals for each purchase order. The new pattern does not allow physical deletion of purchase orders, lines, and markup after it has been confirmed. If this has been done in the previous version, the records will be recreated.

## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchTableVersion</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>PurchTableHistory</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>PurchLineHistory</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>MarkupTransHistory</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VendPurchOrderTrans</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>VendPurchOrderPurchLink</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

