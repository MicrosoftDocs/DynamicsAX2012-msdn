---
title: ReleaseUpdateDB60_Basic.updateWMSBillOfLading_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateWMSBillOfLading_RU Upgrade Script
ms:assetid: 67b6293d-c923-f023-fbc0-4a5b36e8a4c0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685588(v=AX.60)
ms:contentKeyID: 49708790
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateWMSBillOfLading\_RU Upgrade Script 


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
<td><p>updateWMSBillOfLading_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates the AddressTrans_RU table to the new address logic.</p></td>
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
<td><p>WMSBillOfLading</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The DEL\_AddressTrans\_RU table contains the upgraded reference to the LogisticsPostalAddress table

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: WMSBillOfLading</p></th>
<th><p>To Table: DEL_AddressTrans_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LadingPostalAddress_RU</p></td>
<td><p>LogisticsPostalAddresRecId</p></td>
</tr>
<tr class="even">
<td><p>UnladingPostalAddress_RU</p></td>
<td><p>LogisticsPostalAddresRecId</p></td>
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
<th><p>From Table: SalesTable</p></th>
<th><p>To Table: DEL_AddressTrans_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LadingPostalAddress_RU</p></td>
<td><p>LogisticsPostalAddresRecId</p></td>
</tr>
<tr class="even">
<td><p>UnladingPostalAddress_RU</p></td>
<td><p>LogisticsPostalAddresRecId</p></td>
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
<td><p>WMSBillOfLading</p></td>
<td><p>LadingPostalAddress_RU</p></td>
<td><p>LogisticsPostalAddressRecId</p></td>
</tr>
<tr class="even">
<td><p>WMSBillOfLading</p></td>
<td><p>UnladingPostalAddress_RU</p></td>
<td><p>LogisticsPostalAddressRecId</p></td>
</tr>
<tr class="odd">
<td><p>SalesTable</p></td>
<td><p>LadingPostalAddress_RU</p></td>
<td><p>LogisticsPostalAddressRecId</p></td>
</tr>
<tr class="even">
<td><p>SalesTable</p></td>
<td><p>UnladingPostalAddress_RU</p></td>
<td><p>LogisticsPostalAddressRecId</p></td>
</tr>
</tbody>
</table>

  


