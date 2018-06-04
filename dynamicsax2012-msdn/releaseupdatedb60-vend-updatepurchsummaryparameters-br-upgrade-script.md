---
title: ReleaseUpdateDB60_Vend.updatePurchSummaryParameters_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updatePurchSummaryParameters_BR Upgrade Script
ms:assetid: 4fd5e81a-8b4d-f4a6-d7e1-0925ad79ceb7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685514(v=AX.60)
ms:contentKeyID: 49708218
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updatePurchSummaryParameters\_BR Upgrade Script 


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
<td><p>updatePurchSummaryParameters_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method changes the FieldIDs of the fields assigned to determine the summary update criteria for the different types of purchase order updates: Receipt list, packing Slip and invoice.</p></td>
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
<td><p>PurchSummaryParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

Some of the fields that are used as the summary update criteria had their IDs changed in Ax2012. This script updates the PurchSummaryParameters table so that it references the new fields IDs. The fields that will be impacted are: PurchTable.CFOPTable\_BR, PurchTable.SalesPurchOperationType\_BR and PurchTable.FiscalDocumentType\_BR.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

