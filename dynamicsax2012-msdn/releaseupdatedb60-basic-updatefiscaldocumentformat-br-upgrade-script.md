---
title: ReleaseUpdateDB60_Basic.updateFiscalDocumentFormat_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateFiscalDocumentFormat_BR Upgrade Script
ms:assetid: 8ef7ad0b-6aab-7d07-6498-b4dc0ad809b7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736520(v=AX.60)
ms:contentKeyID: 49709709
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateFiscalDocumentFormat\_BR Upgrade Script 


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
<td><p>updateFiscalDocumentFormat_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the FiscalDocumentFormat_BR table with format fields deleted from the FiscalDocumentType_BR table.</p></td>
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
<tr class="even">
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
<td><p>FiscalDocumentFormat_BR</p></td>
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
<th><p>From Table: FiscalDocumentType_BR</p></th>
<th><p>To Table: FiscalDocumentFormat_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MaxItemLines</p></td>
<td><p>MaxItemLines</p></td>
</tr>
<tr class="even">
<td><p>del_MaxItemDescriptionSize</p></td>
<td><p>MaxItemDescriptionSize</p></td>
</tr>
<tr class="odd">
<td><p>del_CutOffItemDescription</p></td>
<td><p>CutOffItemDescription</p></td>
</tr>
<tr class="even">
<td><p>del_MaxMemoLines</p></td>
<td><p>MaxMemoLines</p></td>
</tr>
<tr class="odd">
<td><p>del_MaxMemoDescriptionSize</p></td>
<td><p>MaxMemoDescriptionSize</p></td>
</tr>
<tr class="even">
<td><p>del_CutoffMemoDescription</p></td>
<td><p>CutoffMemoDescription</p></td>
</tr>
<tr class="odd">
<td><p>del_MultiplePagesPerNF</p></td>
<td><p>MultiplePagesPerNF</p></td>
</tr>
<tr class="even">
<td><p>del_MaxServiceItemLines</p></td>
<td><p>MaxServiceItemLines</p></td>
</tr>
<tr class="odd">
<td><p>del_MaxServiceItemDescription</p></td>
<td><p>MaxServiceItemDescription</p></td>
</tr>
<tr class="even">
<td><p>del_CutOffServiceItemDescription</p></td>
<td><p>CutOffServiceItemDescription</p></td>
</tr>
<tr class="odd">
<td><p>del_MaxInstallments</p></td>
<td><p>MaxInstallments</p></td>
</tr>
<tr class="even">
<td><p>del_PrintDlvAddressInMemo</p></td>
<td><p>PrintDlvAddressInMemo</p></td>
</tr>
<tr class="odd">
<td><p>del_eInvoiceExportLayout</p></td>
<td><p>eInvoiceExportLayout</p></td>
</tr>
<tr class="even">
<td><p>del_eInvoiceImportLayout</p></td>
<td><p>eInvoiceImportLayout</p></td>
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
<td><p>FiscalDocumentFormat_BR</p></td>
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
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_MaxItemLines,</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_MaxItemDescriptionSize,</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_CutOffItemDescription,</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_MaxMemoLines,</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_MaxMemoDescriptionSize,</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_CutoffMemoDescription,</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_MultiplePagesPerNF,</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_MaxServiceItemLines,</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_MaxServiceItemDescription,</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_CutOffServiceItemDescription,</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_MaxInstallments,</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_PrintDlvAddressInMemo,</p></td>
</tr>
<tr class="odd">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_eInvoiceExportLayout,</p></td>
</tr>
<tr class="even">
<td><p>FiscalDocumentType_BR</p></td>
<td><p>del_eInvoiceImportLayout,</p></td>
</tr>
</tbody>
</table>

  


