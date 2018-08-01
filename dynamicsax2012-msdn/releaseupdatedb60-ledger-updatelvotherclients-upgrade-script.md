---
title: ReleaseUpdateDB60_Ledger.updateLvOtherClients Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLvOtherClients Upgrade Script
ms:assetid: 1c6a8a23-169c-3635-189a-e121f6f668a2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718707(v=AX.60)
ms:contentKeyID: 49706989
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLvOtherClients Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>updateLvOtherClients</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the information for the LvOtherClients table.</p></td>
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
<td><p>Bank</p></td>
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
<td><p>LvOtherClients</p></td>
</tr>
<tr class="even">
<td><p>OMOperatingUnit</p></td>
</tr>
</tbody>
</table>


## Remarks

This script updates the information in the LvOtherClients table. This includes the new linkage for uptaking the global address book information, instead of storing it as simple text fields. Since there is no way to easily parse street address information, that information is simply stored in its entirety in the Street field of the LogisticalPostalAddress table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LvOtherClients</p></th>
<th><p>To Table: OMOperatingUnit</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Name</p></td>
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
<th><p>From Table: LvOtherClients</p></th>
<th><p>To Table: LvOtherClients</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bank</p></td>
<td><p>Bank</p></td>
</tr>
<tr class="even">
<td><p>BankAccount</p></td>
<td><p>BankAccount</p></td>
</tr>
<tr class="odd">
<td><p>BankAddress</p></td>
<td><p>BankAddress</p></td>
</tr>
<tr class="even">
<td><p>BankRegNum</p></td>
<td><p>BankRegNum</p></td>
</tr>
<tr class="odd">
<td><p>BankSwiftCode</p></td>
<td><p>BankSwiftCode</p></td>
</tr>
<tr class="even">
<td><p>Id</p></td>
<td><p>ClientId</p></td>
</tr>
<tr class="odd">
<td><p>RegNum_LV</p></td>
<td><p>CompRegistNum</p></td>
</tr>
<tr class="even">
<td><p>PaymCode_LV</p></td>
<td><p>LvPaymTransCodes</p></td>
</tr>
<tr class="odd">
<td><p>Resident</p></td>
<td><p>Resident</p></td>
</tr>
<tr class="even">
<td><p>VATNum</p></td>
<td><p>VATNum</p></td>
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
<th><p>From Table: LvOtherClients</p></th>
<th><p>To Table: DirPartyPostalAddressView</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Address</p></td>
<td><p>Street</p></td>
</tr>
<tr class="even">
<td><p>CountryRegionCode</p></td>
<td><p>CountryRegionId</p></td>
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
<td><p>OMOperatingUnit</p></td>
<td><p>Name</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>DirPartyPostalAddressView</p></td>
<td><p>Party</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="odd">
<td><p>DirPartyPostalAddressView</p></td>
<td><p>Street</p></td>
<td><p>LogisticsAddressStreet</p></td>
</tr>
<tr class="even">
<td><p>DirPartyPostalAddressView</p></td>
<td><p>CountryRegionId</p></td>
<td><p>LogisticsAddressCountryRegionId</p></td>
</tr>
</tbody>
</table>

  


