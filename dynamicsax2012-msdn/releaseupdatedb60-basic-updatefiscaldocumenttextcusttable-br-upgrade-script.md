﻿---
title: ReleaseUpdateDB60_Basic.updateFiscalDocumentTextCustTable_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateFiscalDocumentTextCustTable_BR Upgrade Script
ms:assetid: 09ae683b-b6a2-5759-b6de-7bd79040ad61
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735594(v=AX.60)
ms:contentKeyID: 49706504
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateFiscalDocumentTextCustTable\_BR Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateFiscalDocumentTextCustTable_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates all of the Microsoft Dynamics AX 2009 legal texts that are associated with customers to the Microsoft Dynamics AX 2012 fiscal document texts.</p></td>
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
<td><p>DocuRef</p></td>
</tr>
<tr class="even">
<td><p>DocuRefExt_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

This method adds records to the DocuRef and DocuRefExt\_BR tables that are attached to the CustTable records, by using the document handling feature of the core to support the fiscal document texts.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_CustVendLegalTxt_BR</p></th>
<th><p>To Table: DocuRef</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SalesPurchLegalTxt</p></td>
<td><p>Notes</p></td>
</tr>
<tr class="even">
<td><p>SalesPurchLegalTxtInvoiceOnly</p></td>
<td><p>Restriction</p></td>
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
<th><p>From Table: DEL_SalesLegalTxtSetup_BR</p></th>
<th><p>To Table: DocuRef</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SalesLegalTxtDescription</p></td>
<td><p>Name</p></td>
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
<th><p>From Table: CustTable</p></th>
<th><p>To Table: DocuRef</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>TableId</p></td>
<td><p>RefTableId</p></td>
</tr>
<tr class="odd">
<td><p>dataAreaId</p></td>
<td><p>RefCompanyId</p></td>
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
<th><p>From Table: DEL_CustVendLegalTxt_BR</p></th>
<th><p>To Table: DocuRefExt_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FiscalInformationEnabled</p></td>
<td><p>FiscalInformation</p></td>
</tr>
<tr class="even">
<td><p>SalesPurchLegalTxtId</p></td>
<td><p>TextID</p></td>
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
<td><p>DocuRefExt_BR</p></td>
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
<td><p>DEL_CustVendLegalTxt_BR</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

