---
title: ReleaseUpdateDB60_Basic.updateFiscalDocFormat_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateFiscalDocFormat_BR Upgrade Script
ms:assetid: c4927929-f657-e282-30b4-86a179df54fe
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686873(v=AX.60)
ms:contentKeyID: 49711070
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateFiscalDocFormat\_BR Upgrade Script 


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
<td><p>updateFiscalDocFormat_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method migrates the fiscal document formats created during the source system upgrade to AX 2012 fiscal document headers. Not all fiscal document headers will have a fiscal document format associated with them.</p></td>
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
<td><p>FiscalDocument_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the FiscalDocumentFormat field in the FiscalDocument\_BR table with the RecId field of the FiscalDocumentFormat\_BR table that represents the fiscal document format to be associated with the specified fiscal document header.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: FiscalDocumentFormat_BR</p></th>
<th><p>To Table: FiscalDocument_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>FiscalDocumentFormat</p></td>
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
<td><p>DEL_FiscalDocJour_BR</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>DEL_FiscalDocJourUpgrade_BR</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>DEL_CustInvoiceJourUpgrade_BR</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>DEL_VendInvoiceJourUpgrade_BR</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

