---
title: ReleaseUpdateDB60_Cust.updateCustInvoiceLine_IN Upgrade Script
TOCTitle: ReleaseUpdateDB60_Cust.updateCustInvoiceLine_IN Upgrade Script
ms:assetid: 08a10cfd-b893-5006-7eb7-1c3f09b9fb78
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684792(v=AX.60)
ms:contentKeyID: 49706487
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Cust.updateCustInvoiceLine\_IN Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

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
<td><p>updateCustInvoiceLine_IN</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the CustInvoiceLine table. The Record IDs of the Customs tariff code, Excise tariff code and Service code are now stored in place of the CustomsTariffCode_IN, ExciseTariffCode_IN and ServiceCode_IN field values.</p></td>
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
<td><p>CustInvoiceLine</p></td>
</tr>
<tr class="even">
<td><p>CustomsTariffCodeTable_IN</p></td>
</tr>
<tr class="odd">
<td><p>ExciseTariffCodes_IN</p></td>
</tr>
<tr class="even">
<td><p>ServiceCodeTable_IN</p></td>
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
<th><p>From Table: CustomsTariffCodeTable_IN</p></th>
<th><p>To Table: custInvoiceLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>CustomsTariffCodeTable_IN</p></td>
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
<th><p>From Table: ExciseTariffCodes_IN</p></th>
<th><p>To Table: custInvoiceLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ExciseTariffCodes_IN</p></td>
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
<th><p>From Table: ServiceCodeTable_IN</p></th>
<th><p>To Table: custInvoiceLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ServiceCodeTable_IN</p></td>
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
<td><p>custInvoiceLine</p></td>
<td><p>CustomsTariffCodeTable_IN</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>custInvoiceLine</p></td>
<td><p>ExciseTariffCodes_IN</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>custInvoiceLine</p></td>
<td><p>ServiceCodeTable_IN</p></td>
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
<td><p>CustInvoiceLine</p></td>
<td><p>del_CustomsTariffCode_IN</p></td>
</tr>
<tr class="even">
<td><p>CustInvoiceLine</p></td>
<td><p>del_ExciseTariffCode_IN</p></td>
</tr>
<tr class="odd">
<td><p>CustInvoiceLine</p></td>
<td><p>del_ServiceCode_IN</p></td>
</tr>
</tbody>
</table>

  


