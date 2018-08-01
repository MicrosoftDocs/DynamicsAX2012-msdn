---
title: ReleaseUpdateDB60_Proj.updateCustInvoiceJourPrint_HU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateCustInvoiceJourPrint_HU Upgrade Script
ms:assetid: 413e1c0b-a9ba-54ab-8dda-b7d8f5e13e06
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718819(v=AX.60)
ms:contentKeyID: 49707863
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateCustInvoiceJourPrint\_HU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateCustInvoiceJourPrint_HU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script is used for saving information about project invoice printing in the ProjInvoiceJourPrint table. This feature is specific to Hungary.</p></td>
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
<td><p>Accounts receivable</p></td>
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
<td><p>ProjInvoiceJourPrint</p></td>
</tr>
</tbody>
</table>


## Remarks

This script creates new ProjInvoiceJourPrint records for every ProjInvoiceJour record. It copies the value of the CopiesPrinted\_HU and Printed\_HU fields from the ProjInvoiceJour table to the ProjInvoiceJourPrint table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjInvoiceJour</p></th>
<th><p>To Table: ProjInvoiceJourPrint</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CopiesPrinted_HU</p></td>
<td><p>NumberOfCopiesPrinted</p></td>
</tr>
<tr class="even">
<td><p>Printed_HU</p></td>
<td><p>HasOriginalBeenPrinted</p></td>
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
<td><p>ProjInvoiceJourPrint</p></td>
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
<td><p>ProjInvoiceJour</p></td>
<td><p>CopiesPrinted_HU</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceJour</p></td>
<td><p>Printed_HU</p></td>
</tr>
</tbody>
</table>

  


