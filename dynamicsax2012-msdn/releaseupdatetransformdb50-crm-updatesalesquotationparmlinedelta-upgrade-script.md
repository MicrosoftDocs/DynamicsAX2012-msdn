---
title: ReleaseUpdateTransformDB50_CRM.updateSalesQuotationParmLineDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_CRM.updateSalesQuotationParmLineDelta Upgrade Script
ms:assetid: 38b90bea-b8ea-fcd1-c96b-4834fd17cec0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685214(v=AX.60)
ms:contentKeyID: 49707666
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_CRM.updateSalesQuotationParmLineDelta Upgrade Script 


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
<td><p>updateSalesQuotationParmLineDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the delivery postal address in the SalesQuotationParmLine table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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
<td><p>SalesQuotationParmLine</p></td>
</tr>
<tr class="even">
<td><p>Shadow_SalesQuotationParmLine_GAB</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsPostalAddress</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to uptake to the new logistics postal address model for Microsoft Dynamics AX 2012. The delivery postal address for the SalesQuotationParmLine will be kept as a reference to the LogisticsPostalAddress record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LogisticsPostalAddress</p></th>
<th><p>To Table: Shadow_SalesQuotationParmLine_GAB</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>DeliveryPostalAddress</p></td>
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
<th><p>From Table: SalesQuotationParmLine</p></th>
<th><p>To Table: Shadow_SalesQuotationParmLine_GAB</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>recVersion</p></td>
<td><p>RecVersionId</p></td>
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
<td><p>SalesQuotationParmLine</p></td>
<td><p>DeliveryPostalAdress</p></td>
<td><p>LogisticsPostalAddressRecId</p></td>
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
<td><p>SalesQuotationParmLine</p></td>
<td><p>DeliveryAddress</p></td>
</tr>
</tbody>
</table>

  


