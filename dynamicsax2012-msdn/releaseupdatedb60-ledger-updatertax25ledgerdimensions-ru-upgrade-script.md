---
title: ReleaseUpdateDB60_Ledger.updateRTax25LedgerDimensions_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateRTax25LedgerDimensions_RU Upgrade Script
ms:assetid: cae63b0e-b6ef-2b8c-5f69-aa3bcf3f844b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719651(v=AX.60)
ms:contentKeyID: 49711218
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateRTax25LedgerDimensions\_RU Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateRTax25LedgerDimensions_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the DimensionAttribute fields in the RTax25Parameters table. Converts data from the old account fields to the new LedgerDimension type in the RTax25LedgerInterval, RTax25RegisterParameters, and RTax25TaxTable tables.</p></td>
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
<td><p>RTax25Parameters</p></td>
</tr>
<tr class="even">
<td><p>RTax25LedgerInterval</p></td>
</tr>
<tr class="odd">
<td><p>RTax25RegisterParameters</p></td>
</tr>
<tr class="even">
<td><p>RTax25TaxTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert account/dimension data to the new accounts and dimension model for 6.0.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: RTax25LedgerInterval</p></th>
<th><p>To Table: RTax25LedgerInterval</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AccountFrom</p></td>
<td><p>FromMainAccountId</p></td>
</tr>
<tr class="even">
<td><p>AccountTo</p></td>
<td><p>ToMainAccountId</p></td>
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
<th><p>From Table: RTax25RegisterParameters</p></th>
<th><p>To Table: RTax25RegisterParameters</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Parameter</p></td>
<td><p>LedgerDimension</p></td>
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
<th><p>From Table: RTax25TaxTable</p></th>
<th><p>To Table: RTax25TaxTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExportVATFineLedgerAccount</p></td>
<td><p>ExportVATFineLedgerDimension</p></td>
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
<td><p>RTax25LedgerInterval</p></td>
<td><p>FromMainAccountId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>RTax25LedgerInterval</p></td>
<td><p>ToMainAccountId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>RTax25RegisterParameters</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="even">
<td><p>RTax25TaxTable</p></td>
<td><p>ExportVATFineLedgerDimension</p></td>
<td><p>LedgerDimensionDefaultAccount</p></td>
</tr>
<tr class="odd">
<td><p>RTax25Parameters</p></td>
<td><p>DimensionAttribute</p></td>
<td><p>RefRecId</p></td>
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
<td><p>RTax25LedgerInterval</p></td>
<td><p>AccountFrom</p></td>
</tr>
<tr class="even">
<td><p>RTax25LedgerInterval</p></td>
<td><p>AccountTo</p></td>
</tr>
<tr class="odd">
<td><p>RTax25TaxTable</p></td>
<td><p>ExportVATFineLedgerAccount</p></td>
</tr>
</tbody>
</table>

  


