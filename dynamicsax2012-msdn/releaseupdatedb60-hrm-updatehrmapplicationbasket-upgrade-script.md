---
title: ReleaseUpdateDB60_HRM.updateHRMApplicationBasket Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMApplicationBasket Upgrade Script
ms:assetid: ccdf90a0-0d34-b6dc-a9dc-3791d1873e19
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719708(v=AX.60)
ms:contentKeyID: 49711274
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMApplicationBasket Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_HRM</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHRMApplicationBasket</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Person field in the HRMApplicationBasket table.</p></td>
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
<td><p>Human Resources</p></td>
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
<td><p>EmplTable</p></td>
</tr>
<tr class="even">
<td><p>HcmApplicant</p></td>
</tr>
<tr class="odd">
<td><p>HRMApplicationBasket</p></td>
</tr>
<tr class="even">
<td><p>HcmApplicationBasketLocation</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="even">
<td><p>LogisticsPostalAddress</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsElectronicAddress</p></td>
</tr>
</tbody>
</table>


## Remarks

Inserts records in the LogisticsLocation table, the LogisticsPostalAddress table, the LogisticsElectronicAddress table, and the ApplicationBasketLocation table for the address and contact information stored in HRMApplicationBasket table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: HRMApplicationBasket</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CountryRegionId</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="even">
<td><p>State</p></td>
<td><p>State</p></td>
</tr>
<tr class="odd">
<td><p>County</p></td>
<td><p>County</p></td>
</tr>
<tr class="even">
<td><p>City</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>ZipCode</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
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
<th><p>From Table: HRMApplicationBasket</p></th>
<th><p>To Table: LogisticsElectronicAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Phone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="even">
<td><p>CellularPhone</p></td>
<td><p>Locator</p></td>
</tr>
<tr class="odd">
<td><p>Email</p></td>
<td><p>Locator</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name:</p></th>
<th><p>New Table Name:</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>CountryRegionId</p></td>
<td><p>DEL_CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>State</p></td>
<td><p>DEL_State</p></td>
</tr>
<tr class="even">
<td><p>County</p></td>
<td><p>DEL_County</p></td>
</tr>
<tr class="odd">
<td><p>City</p></td>
<td><p>DEL_City</p></td>
</tr>
<tr class="even">
<td><p>Street</p></td>
<td><p>DEL_Street</p></td>
</tr>
<tr class="odd">
<td><p>EmplId</p></td>
<td><p>DEL_EmplId</p></td>
</tr>
<tr class="even">
<td><p>Address</p></td>
<td><p>DEL_Address</p></td>
</tr>
<tr class="odd">
<td><p>Phone</p></td>
<td><p>DEL_Phone</p></td>
</tr>
<tr class="even">
<td><p>CellularPhone</p></td>
<td><p>DEL_CellularPhone</p></td>
</tr>
<tr class="odd">
<td><p>Email</p></td>
<td><p>DEL_Email</p></td>
</tr>
<tr class="even">
<td><p>StoreApplication</p></td>
<td><p>DEL_StoreApplication</p></td>
</tr>
<tr class="odd">
<td><p>ZipCode</p></td>
<td><p>DEL_ZipCode</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

