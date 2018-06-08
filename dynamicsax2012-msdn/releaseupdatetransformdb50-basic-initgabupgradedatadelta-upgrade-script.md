---
title: ReleaseUpdateTransformDB50_Basic.initGABUpgradeDataDelta Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Basic.initGABUpgradeDataDelta Upgrade Script
ms:assetid: 1782e094-208d-79dc-ede4-6fbe19b2ff2c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718583(v=AX.60)
ms:contentKeyID: 49706867
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Basic.initGABUpgradeDataDelta Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>initGABUpgradeDataDelta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the address format in the AddressFormatHeading table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
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
<td><p>AddressFormatHeading</p></td>
</tr>
<tr class="even">
<td><p>AddressFormatLines</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert the address format data to the new logistics postal address model for Microsoft Dynamics AX 2012. Only one address format of a company is being upgraded to Microsoft Dynamics AX 2012, based on the user selection on the DirCountryRegionCodes form.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AddressFormatHeading</p></th>
<th><p>To Table: LogisticsAddressFormatHeading</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AddrFormat</p></td>
<td><p>AddrFormat</p></td>
</tr>
<tr class="even">
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
<th><p>From Table: AddressFormatLines</p></th>
<th><p>To Table: LogisticsAddressFormatLines</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>LineNum</p></td>
<td><p>LineNum</p></td>
</tr>
<tr class="even">
<td><p>InActive</p></td>
<td><p>InActive</p></td>
</tr>
<tr class="odd">
<td><p>Separator</p></td>
<td><p>Separator</p></td>
</tr>
<tr class="even">
<td><p>Element</p></td>
<td><p>Element</p></td>
</tr>
<tr class="odd">
<td><p>Expand</p></td>
<td><p>Expand</p></td>
</tr>
<tr class="even">
<td><p>Special</p></td>
<td><p>Special</p></td>
</tr>
<tr class="odd">
<td><p>NumOfSpaces</p></td>
<td><p>NumOfSpaces</p></td>
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
<td><p>LogisticsAddressFormatHeading</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddressFormatLines</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>AddressFormatHeading</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>AddressFormatLines</p></td>
<td><p>*</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

