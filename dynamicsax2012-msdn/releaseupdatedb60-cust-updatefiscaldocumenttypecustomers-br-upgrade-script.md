---
title: ReleaseUpdateDB60_Cust.updateFiscalDocumentTypeCustomers_BR Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateFiscalDocumentTypeCustomers_BR Upgrade Script
ms:assetid: 45f71a7b-2430-5285-16e5-0f02f43b8581
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718948(v=AX.60)
ms:contentKeyID: 49707982
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateFiscalDocumentTypeCustomers\_BR Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateFiscalDocumentTypeCustomers_BR</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates vendor fiscal document type configuration for each vendor that has fiscal document type configured.</p></td>
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
<td><p>VendFiscalDocumentType_BR</p></td>
</tr>
</tbody>
</table>


## Remarks

The VendFiscalDocumentType\_BR table is used to enable the configuration of fiscal document type to be used on purchase order for a specific vendor, a group of vendors or for all vendors when is necessary issue a fiscal document.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: VendTable</p></th>
<th><p>To Table: CustFiscalDocumentType_BR</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountNum</p></td>
<td><p>AccountRelation</p></td>
</tr>
<tr class="even">
<td><p>del_VendInvoiceType_BR</p></td>
<td><p>FiscalDocumentType_BR</p></td>
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
<td><p>VendFiscalDocumentType_BR</p></td>
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
<td><p>VendTable</p></td>
<td><p>del_VendInvoiceType_BR</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

