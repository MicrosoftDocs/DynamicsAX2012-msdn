---
title: ReleaseUpdateDB60_Ledger.updateCustomsVendBOEJour_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateCustomsVendBOEJour_IN Upgrade Script
ms:assetid: 35680c15-a2f2-0be3-c385-c6892f9a7460
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685150(v=AX.60)
ms:contentKeyID: 49707603
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateCustomsVendBOEJour\_IN Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCustomsVendBOEJour_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the value for the CustomsBillOfEntryNumberTable and CustomsImportInvoiceNumberTable fields in the CustomsVendBOEJour_IN table.</p></td>
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
<td><p>Ledger</p></td>
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
<td><p>CustomsBillOfEntryNumberTable_IN</p></td>
</tr>
<tr class="even">
<td><p>CustomsImportInvoiceNumberTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>CustomsVendBOEJour_IN</p></td>
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
<th><p>From Table: CustomsBillOfEntryNumberTable_IN</p></th>
<th><p>To Table: CustomsVendBOEJour_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CustomsBillOfEntryNumberTable</p></td>
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
<th><p>From Table: CustomsImportInvoiceNumberTable_IN</p></th>
<th><p>To Table: CustomsVendBOEJour_IN</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CustomsImportInvoiceNumberTable</p></td>
</tr>
</tbody>
</table>


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
<td><p>CustomsVendBOEJour_IN</p></td>
<td><p>CustomsBillOfEntryNumberTable</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>CustomsVendBOEJour_IN</p></td>
<td><p>CustomsImportInvoiceNumberTable</p></td>
<td><p>RefRecId</p></td>
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
<td><p>CustomsVendBOEJour_IN</p></td>
<td><p>DEL_BillOfEntryNumber</p></td>
</tr>
<tr class="even">
<td><p>CustomsVendBOEJour_IN</p></td>
<td><p>DEL_ImportInvoiceNumber</p></td>
</tr>
</tbody>
</table>

  


