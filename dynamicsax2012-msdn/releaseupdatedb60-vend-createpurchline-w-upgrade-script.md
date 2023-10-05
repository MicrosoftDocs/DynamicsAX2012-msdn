---
title: ReleaseUpdateDB60_Vend.createPurchLine_W Upgrade Script
TOCTitle: ReleaseUpdateDB60_Vend.createPurchLine_W Upgrade Script
ms:assetid: 23ed17fe-cc74-6556-0562-1ee1fd79dc45
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684981(v=AX.60)
ms:contentKeyID: 49707183
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Vend.createPurchLine\_W Upgrade Script 


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
<td><p>createPurchLine_W</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates country/region specific fields from the &lt;c&gt;PurchLine&lt;/c&gt; table to &lt;c&gt;PurchLine_W&lt;/c&gt; table</p></td>
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
<td><p>PurchLine</p></td>
</tr>
<tr class="even">
<td><p>PurchLine_W</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates all purchase lines linked to Inventory Table which meet the following condition: Type is Service, MarkupCode\_RU is not empty.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchLine</p></th>
<th><p>To Table: PurchLine_W</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CountryRegionName_RU</p></td>
<td><p>CountryRegionName_RU</p></td>
</tr>
<tr class="even">
<td><p>DeviationQty_RU</p></td>
<td><p>DeviationQty_RU</p></td>
</tr>
<tr class="odd">
<td><p>InvoiceGTDId_RU</p></td>
<td><p>InvoiceGTDId_RU</p></td>
</tr>
<tr class="even">
<td><p>MarkupCode_RU</p></td>
<td><p>MarkupCode_RU</p></td>
</tr>
<tr class="odd">
<td><p>PostingProfile_RU</p></td>
<td><p>PostingProfile_RU</p></td>
</tr>
<tr class="even">
<td><p>PriceAgreementDate_RU</p></td>
<td><p>PriceAgreementDate_RU</p></td>
</tr>
<tr class="odd">
<td><p>RefReturnInvoiceTrans_W</p></td>
<td><p>RefReturnInvoiceTrans_W</p></td>
</tr>
<tr class="even">
<td><p>SadInvoiceLineNo_PL</p></td>
<td><p>SadInvoiceLineNo_PL</p></td>
</tr>
</tbody>
</table>

  


