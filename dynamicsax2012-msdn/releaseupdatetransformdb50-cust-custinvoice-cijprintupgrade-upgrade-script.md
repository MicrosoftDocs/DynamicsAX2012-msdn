---
title: ReleaseUpdateTransformDB50_Cust.CustInvoice_CIJPrintUpgrade Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Cust.CustInvoice_CIJPrintUpgrade Upgrade Script
ms:assetid: 09f61166-2431-ca3b-be16-b5d51ec64009
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735605(v=AX.60)
ms:contentKeyID: 49706516
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Cust.CustInvoice\_CIJPrintUpgrade Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>CustInvoice_CIJPrintUpgrade</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script is used for saving the printed sales invoice document information in the &lt;c&gt;CustInvoiceJourPrint&lt;/c&gt; table with the new data model.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>CustInvoiceJourPrint</p></td>
</tr>
</tbody>
</table>


## Remarks

This script creates new \<c\>CustInvoiceJourPrint\</c\> records for every \<c\>CustInvoiceJour\</c\> record which have print information saved. It copies \<c\>CopiesPrinted\_HU\</c\> and \<c\>Printed\_HU\</c\> field from \<c\>CustInvoiceJour\</c\> table to \<c\>CustInvoiceJourPrint\</c\> table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: CustInvoiceJourPrint</p></th>
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
<td><p>CustInvoiceJourPrint</p></td>
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
<td><p>CustInvoiceJour</p></td>
<td><p>CopiesPrinted_HU</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceJour</p></td>
<td><p>Printed_HU</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

