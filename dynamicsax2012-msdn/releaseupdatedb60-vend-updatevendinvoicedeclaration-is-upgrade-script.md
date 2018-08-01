---
title: ReleaseUpdateDB60_Vend.updateVendInvoiceDeclaration_IS Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.updateVendInvoiceDeclaration_IS Upgrade Script
ms:assetid: fdd24f16-2758-9c55-40b9-24be248aba89
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720141(v=AX.60)
ms:contentKeyID: 49712446
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.updateVendInvoiceDeclaration\_IS Upgrade Script 


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
<td><p>updateVendInvoiceDeclaration_IS</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the VendTable, PurchTable, LedgerJournalTrans, and VendInvoiceJour tables. These tables now hold the RecID field instead of the declarationID field from the VendInvoiceDeclaration_IS table.</p></td>
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
<td><p>LedgerJournalTrans</p></td>
</tr>
<tr class="even">
<td><p>PurchTable</p></td>
</tr>
<tr class="odd">
<td><p>VendInvoiceDeclaration_IS</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceJour</p></td>
</tr>
<tr class="odd">
<td><p>VendTable</p></td>
</tr>
</tbody>
</table>

  


