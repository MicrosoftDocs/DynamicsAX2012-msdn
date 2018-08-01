---
title: ReleaseUpdateDB60_Basic.createBooksDirPartyProperties_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.createBooksDirPartyProperties_RU Upgrade Script
ms:assetid: f5bc8f28-9e37-798f-93c7-ea5321000ae2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737544(v=AX.60)
ms:contentKeyID: 49712238
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.createBooksDirPartyProperties\_RU Upgrade Script 


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
<td><p>createBooksDirPartyProperties_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates properties specific to the release update from DirParty related tables.</p></td>
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
<tr class="even">
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
<td><p>PurchBookTrans_RU</p></td>
</tr>
<tr class="even">
<td><p>PurchBookVATProcessLogTrans_RU</p></td>
</tr>
<tr class="odd">
<td><p>SalesBookTrans_RU</p></td>
</tr>
<tr class="even">
<td><p>SalesBookVATProcessLogTrans_RU</p></td>
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
<th><p>From Table: PurchBookTrans_RU</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>INN</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>KPP</p></td>
<td><p>Value</p></td>
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
<th><p>From Table: PurchBookVATProcessLogTrans_RU</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>INN</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>KPP</p></td>
<td><p>Value</p></td>
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
<th><p>From Table: SalesBookTrans_RU</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>INN</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>KPP</p></td>
<td><p>Value</p></td>
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
<th><p>From Table: SalesBookVATProcessLogTrans_RU</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>INN</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>KPP</p></td>
<td><p>Value</p></td>
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
<td><p>DirPartyProperty_RU</p></td>
<td><p>Type</p></td>
<td><p>DirPartyPropertyType_RU</p></td>
</tr>
<tr class="even">
<td><p>DirPartyProperty_RU</p></td>
<td><p>Value</p></td>
<td><p>DirPartyPropertyValue_RU</p></td>
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
<td><p>PurchBookTrans_RU</p></td>
<td><p>INN</p></td>
</tr>
<tr class="even">
<td><p>PurchBookTrans_RU</p></td>
<td><p>KPP</p></td>
</tr>
<tr class="odd">
<td><p>PurchBookVATProcessLogTrans_RU</p></td>
<td><p>INN</p></td>
</tr>
<tr class="even">
<td><p>PurchBookVATProcessLogTrans_RU</p></td>
<td><p>KPP</p></td>
</tr>
<tr class="odd">
<td><p>SalesBookTrans_RU</p></td>
<td><p>INN</p></td>
</tr>
<tr class="even">
<td><p>SalesBookTrans_RU</p></td>
<td><p>KPP</p></td>
</tr>
<tr class="odd">
<td><p>SalesBookVATProcessLogTrans_RU</p></td>
<td><p>INN</p></td>
</tr>
<tr class="even">
<td><p>SalesBookVATProcessLogTrans_RU</p></td>
<td><p>KPP</p></td>
</tr>
</tbody>
</table>

  


