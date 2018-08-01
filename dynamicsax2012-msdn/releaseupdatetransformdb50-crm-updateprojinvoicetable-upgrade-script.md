---
title: ReleaseUpdateTransformDB50_CRM.updateProjInvoiceTable Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_CRM.updateProjInvoiceTable Upgrade Script
ms:assetid: 9ed2bef8-efca-632c-8b8a-1ae22b5c1b0b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736655(v=AX.60)
ms:contentKeyID: 49710097
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_CRM.updateProjInvoiceTable Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_CRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateProjInvoiceTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the delivery postal address in the ProjInvoiceTable table.</p></td>
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
<td><p>Project</p></td>
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
<td><p>ProjInvoiceTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert postal address data to the new logistics postal address model for Microsoft Dynamics AX 2012. The delivery postal address for the ProjInvoiceTable table will be kept as a reference to the LogisticsPostalAddress record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjInvoiceTable</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Addr</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>CountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>State</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>CountyId</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>ZipCodeId</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
<td><p>City</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>Street</p></td>
<td><p>Street</p></td>
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
<th><p>From Table: LogisticsPostalAddress</p></th>
<th><p>To Table: Shadow_ProjInvoiceTable_GAB</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Location</p></td>
<td><p>InvoiceLocation</p></td>
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
<td><p>ProjInvoiceTable</p></td>
<td><p>InvoiceLocation</p></td>
<td><p>LogisticsLocationRecId</p></td>
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
<td><p>ProjInvoiceTable</p></td>
<td><p>Addr</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceTable</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceTable</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceTable</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceTable</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
<td><p>ProjInvoiceTable</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>ProjInvoiceTable</p></td>
<td><p>Street</p></td>
</tr>
</tbody>
</table>

  


