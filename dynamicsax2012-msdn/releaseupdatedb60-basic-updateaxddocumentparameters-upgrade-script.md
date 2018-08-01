---
title: ReleaseUpdateDB60_Basic.updateAxdDocumentParameters Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateAxdDocumentParameters Upgrade Script
ms:assetid: 21a9956a-e3d0-ba15-fe14-eb467c8f0256
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684929(v=AX.60)
ms:contentKeyID: 49707131
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateAxdDocumentParameters Upgrade Script 


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
<td><p>updateAxdDocumentParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the FreeTextInvoiceLedgerDimension field in the AxdDocumentParameters table.</p></td>
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
<td><p>AxdDocumentParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

Sets the FreeTextInvoiceLedgerDimension field with data that is converted from the LedgerDimensionDefaultAccount field.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AxdDocumentParameters</p></th>
<th><p>To Table: AxdDocumentParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FreeTextInvoiceLedgerAccount</p></td>
<td><p>FreeTextInvoiceLedgerDimension</p></td>
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
<td><p>AxdDocumentParameters</p></td>
<td><p>FreeTextInvoiceLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
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
<td><p>AxdDocumentParameters</p></td>
<td><p>FreeTextInvoiceLedgerAccount</p></td>
</tr>
</tbody>
</table>

  


