---
title: ReleaseUpdateDB60_Basic.updateEUSalesListReferences Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateEUSalesListReferences Upgrade Script
ms:assetid: 51c04755-0f1c-af31-956d-50837c535798
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685534(v=AX.60)
ms:contentKeyID: 49708238
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateEUSalesListReferences Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEUSalesListReferences</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates tables using the Eastern European specific fields for the EU sales list by moving the values to the generic fields instead.</p></td>
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
<td><p>General ledger</p></td>
</tr>
<tr class="even">
<td><p>Basic</p></td>
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
<td><p>VendInvoiceJour</p></td>
</tr>
<tr class="odd">
<td><p>VendSettlement</p></td>
</tr>
<tr class="even">
<td><p>CustSettlement</p></td>
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
<th><p>To Table: PurchTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_ListCode_EE</p></td>
<td><p>ListCode</p></td>
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
<th><p>From Table: VendInvoiceJour</p></th>
<th><p>To Table: VendInvoiceJour</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_ListCode_EE</p></td>
<td><p>ListCode</p></td>
</tr>
<tr class="even">
<td><p>DEL_EUSalesList_HU</p></td>
<td><p>EUSalesList</p></td>
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
<th><p>From Table: VendSettlement</p></th>
<th><p>To Table: VendSettlement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_EUSalesList_W</p></td>
<td><p>EUSalesList</p></td>
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
<th><p>From Table: CustSettlement</p></th>
<th><p>To Table: CustSettlement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_EUSalesList_W</p></td>
<td><p>EUSalesList</p></td>
</tr>
</tbody>
</table>

  


