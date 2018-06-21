---
title: ReleaseUpdateTransformDB40_Ledger.updateReferencedCustInvoiceJour_BR Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Ledger.updateReferencedCustInvoiceJour_BR Upgrade Script
ms:assetid: 41666a41-7c34-c731-5cf4-61548a8b90f2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718831(v=AX.60)
ms:contentKeyID: 49707875
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Ledger.updateReferencedCustInvoiceJour\_BR Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateReferencedCustInvoiceJour_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This script is used for updating the referenced fiscal documents from customer invoices.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p>
<p>Pre-processing60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>DEL_ReferencedFiscalDocJourUpgrade_BR</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocument_BR</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentReferenced_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

The script updates the \<c\>FiscalDocument\_BR\</c\> table \<c\>ComplementedFiscalDocument\</c\> field and creates the \<c\>FiscalDocumentReferenced\_BR\</c\> table records.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: CustInvoiceJour</p></th>
<th><p>To Table: DEL_ReferencedFiscalDocJourUpgrade_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocJourRecId</p></td>
</tr>
<tr class="even">
<td><p>RecVersion</p></td>
<td><p>RecVersionId</p></td>
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
<th><p>From Table: FiscalDocument_BR</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ComplementedFiscalDocument</p></td>
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
<th><p>From Table: FiscalDocument_BR</p></th>
<th><p>To Table: FiscalDocumentReferenced_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocument</p></td>
</tr>
<tr class="even">
<td><p>RecId</p></td>
<td><p>ReferencedFiscalDocument</p></td>
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
<th><p>From Table: FiscalReference_BR</p></th>
<th><p>To Table: FiscalDocumentReferenced_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LegalTextId</p></td>
<td><p>FiscalDocumentSourceText</p></td>
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
<th><p>From Table: ExternalInvoiceInfo_BR</p></th>
<th><p>To Table: FiscalDocumentReferenced_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ExternalReferencedFiscalDocument</p></td>
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
<td><p>FiscalDocument_BR</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentReferenced_BR</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

