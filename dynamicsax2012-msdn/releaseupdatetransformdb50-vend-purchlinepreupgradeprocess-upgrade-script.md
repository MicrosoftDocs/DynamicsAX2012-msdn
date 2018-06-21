---
title: ReleaseUpdateTransformDB50_Vend.purchLinePreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Vend.purchLinePreUpgradeProcess Upgrade Script
ms:assetid: c4328bca-2838-4310-db5e-dcc824ba65fa
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686850(v=AX.60)
ms:contentKeyID: 49711047
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Vend.purchLinePreUpgradeProcess Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Vend</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>purchLinePreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Sets the line numbers and the reference to the SourceDocumentLine records for the PurchLine records.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p>
<p>Microsoft Dynamics AX 2009</p></td>
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
</tbody>
</table>


## Remarks

For each PurchLine record, the SourceDocumentLine records is created. The value of the SourceDocument field is set to the same value of the field of the Shadow\_PurchTable\_Vend table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: Shadow_PurchTable_Vend</p></th>
<th><p>To Table: SourceDocumentLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SourceDocument</p></td>
<td><p>SourceDocument</p></td>
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
<th><p>From Table: SourceDocumentLine</p></th>
<th><p>To Table: Shadow_PurchLine_Vend</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SourceDocumentLine</p></td>
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
<td><p>SourceDocumentLine</p></td>
<td><p>SourceDocument</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>PurchLine</p></td>
<td><p>SourceDocumentLine</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>PurchLine</p></td>
<td><p>LineNumber</p></td>
<td><p>TradeLineNumber</p></td>
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
<td><p>VendInvoiceTrans</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="even">
<td><p>VendInvoiceTrans</p></td>
<td><p>LedgerAccount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

