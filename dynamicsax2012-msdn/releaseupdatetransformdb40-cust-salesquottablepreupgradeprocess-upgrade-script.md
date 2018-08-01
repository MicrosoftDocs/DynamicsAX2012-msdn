---
title: ReleaseUpdateTransformDB40_Cust.salesQuotTablePreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Cust.salesQuotTablePreUpgradeProcess Upgrade Script
ms:assetid: 483d7c74-1c86-9d11-3f2b-a5bdaa4ead9b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685324(v=AX.60)
ms:contentKeyID: 49708018
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Cust.salesQuotTablePreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Cust</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>salesQuotTablePreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Transforms data from the Dimension field to the DefaultDimension field, from the SalesTaker field to the WorkerSalesTaker field, and from the SalesResponsible field to the PersonSalesResponsible field in the SalesQuotationTable table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
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
<td><p>SalesQuotationTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This is a combined upgrade used to convert account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012 and to convert employee data to a new HRM model.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: SalesQuotationTable</p></th>
<th><p>To Table: Shadow_SalesQuotationTable_DimAndHcmWrk</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimension</p></td>
</tr>
<tr class="even">
<td><p>SalesTaker</p></td>
<td><p>WorkerSalesTaker</p></td>
</tr>
<tr class="odd">
<td><p>SalesResponsible</p></td>
<td><p>PersonSalesResponsible</p></td>
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
<td><p>SalesQuotationTable</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
<tr class="even">
<td><p>SalesQuotationTable</p></td>
<td><p>WorkerSalesTaker</p></td>
<td><p>SalesTaker</p></td>
</tr>
<tr class="odd">
<td><p>SalesQuotationTable</p></td>
<td><p>PersonSalesResponsible</p></td>
<td><p>SalesResponsible</p></td>
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
<td><p>Shadow_SalesQuotationTable_DimAndHcmWrk</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="even">
<td><p>Shadow_SalesQuotationTable_DimAndHcmWrk</p></td>
<td><p>SalesTaker</p></td>
</tr>
<tr class="odd">
<td><p>Shadow_SalesQuotationTable_DimAndHcmWrk</p></td>
<td><p>SalesResponsible</p></td>
</tr>
</tbody>
</table>

  


