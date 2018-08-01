---
title: ReleaseUpdateDB60_Basic.updateFiscalDocumentSourceText_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateFiscalDocumentSourceText_BR Upgrade Script
ms:assetid: 75ad375f-cf8f-c18d-0aa1-f777c1efaeac
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719324(v=AX.60)
ms:contentKeyID: 49709116
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateFiscalDocumentSourceText\_BR Upgrade Script 


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
<td><p>updateFiscalDocumentSourceText_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates all of the Microsoft Dynamics AX 2009 legal text that are associated with setup records to Microsoft Dynamics AX 2012 fiscal document texts.</p></td>
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
<td><p>FiscalDocumentSourceText_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

This method uses the pre-processing script information to avoid duplicate text IDs because the sales and purchase flag is not used anymore. It also creates fiscal document source texts for formerly hard-coded legal texts that were used in direct import and tax withholding features.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: DEL_SalesLegalTxtSetup_BR</p></th>
<th><p>To Table: FiscalDocumentSourceText_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SalesLegalTxtDescription</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>SalesLegalTxt</p></td>
<td><p>Notes</p></td>
</tr>
<tr class="odd">
<td><p>SalesLegalTxtInvoiceOnly</p></td>
<td><p>Restriction</p></td>
</tr>
<tr class="even">
<td><p>FiscalInformationEnabled</p></td>
<td><p>FiscalInformation</p></td>
</tr>
<tr class="odd">
<td><p>SalesLegalTxtId</p></td>
<td><p>TextID</p></td>
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
<th><p>From Table: DEL_PurchLegalTxtSetup_BR</p></th>
<th><p>To Table: FiscalDocumentSourceText_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchLegalTxtDescription</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>PurchLegalTxt</p></td>
<td><p>Notes</p></td>
</tr>
<tr class="odd">
<td><p>PurchLegalTxtInvoiceOnly</p></td>
<td><p>Restriction</p></td>
</tr>
<tr class="even">
<td><p>FiscalInformationEnabled</p></td>
<td><p>FiscalInformation</p></td>
</tr>
<tr class="odd">
<td><p>PurchLegalTxtId</p></td>
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
<td><p>FiscalDocumentSourceText_BR</p></td>
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
<td><p>DEL_SalesLegalTxtSetup_BR</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>DEL_PurchLegalTxtSetup_BR</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  


