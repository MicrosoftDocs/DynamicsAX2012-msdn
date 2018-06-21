---
title: ReleaseUpdateDB60_Basic.createDirPartyProperties_RU Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.createDirPartyProperties_RU Upgrade Script
ms:assetid: d364fae5-2b00-07b3-dd41-8afa082c7d31
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686998(v=AX.60)
ms:contentKeyID: 49711448
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.createDirPartyProperties\_RU Upgrade Script [AX 2012]


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
<td><p>createDirPartyProperties_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Migrates RU specific properties from the DirParty tables.</p></td>
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
<tr class="odd">
<td><p>Basic</p></td>
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
<td><p>DirPartyTable</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
</tr>
<tr class="odd">
<td><p>VendTable</p></td>
</tr>
<tr class="even">
<td><p>CustTable</p></td>
</tr>
<tr class="odd">
<td><p>EmplTable</p></td>
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
<th><p>From Table: DirPartyTable</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>INN</p></td>
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
<th><p>From Table: CompanyInfo</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>INN_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>KPPU_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>OGRN_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>OKATO_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>OKDP_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>OKPO_RU</p></td>
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
<th><p>From Table: VendTable</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>INN_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>KPPU_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>OKATO_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>OKDP_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>OKPO_RU</p></td>
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
<th><p>From Table: CustTable</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>INN_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>KPPU_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>OKATO_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="even">
<td><p>CodeOKDP_RU</p></td>
<td><p>Value</p></td>
</tr>
<tr class="odd">
<td><p>CodeOKPO_RU</p></td>
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
<th><p>From Table: EmplTable</p></th>
<th><p>To Table: DirPartyProperty_RU</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PayINN_RU</p></td>
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
<td><p>DirPartyTable</p></td>
<td><p>INN_RU</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>INN_RU</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>KPPU_RU</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>OGRN_RU</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>OKATO_RU</p></td>
</tr>
<tr class="even">
<td><p>CompanyInfo</p></td>
<td><p>OKDP_RU</p></td>
</tr>
<tr class="odd">
<td><p>CompanyInfo</p></td>
<td><p>OKPO_RU</p></td>
</tr>
<tr class="even">
<td><p>VendTable</p></td>
<td><p>INN_RU</p></td>
</tr>
<tr class="odd">
<td><p>VendTable</p></td>
<td><p>KPPU_RU</p></td>
</tr>
<tr class="even">
<td><p>VendTable</p></td>
<td><p>OKATO_RU</p></td>
</tr>
<tr class="odd">
<td><p>VendTable</p></td>
<td><p>OKDP_RU</p></td>
</tr>
<tr class="even">
<td><p>VendTable</p></td>
<td><p>OKPO_RU</p></td>
</tr>
<tr class="odd">
<td><p>CustTable</p></td>
<td><p>INN_RU</p></td>
</tr>
<tr class="even">
<td><p>CustTable</p></td>
<td><p>KPPU_RU</p></td>
</tr>
<tr class="odd">
<td><p>CustTable</p></td>
<td><p>OKATO_RU</p></td>
</tr>
<tr class="even">
<td><p>CustTable</p></td>
<td><p>CodeOKDP_RU</p></td>
</tr>
<tr class="odd">
<td><p>CustTable</p></td>
<td><p>CodeOKPO_RU</p></td>
</tr>
<tr class="even">
<td><p>EmplTable</p></td>
<td><p>PayINN_RU</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

