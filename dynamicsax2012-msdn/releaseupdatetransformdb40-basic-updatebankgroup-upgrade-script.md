---
title: ReleaseUpdateTransformDB40_Basic.updateBankGroup Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Basic.updateBankGroup Upgrade Script
ms:assetid: efa6587f-8130-488e-0153-ae591b185128
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720031(v=AX.60)
ms:contentKeyID: 49712083
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Basic.updateBankGroup Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateBankGroup</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the postal address in the &lt;c&gt;BankGroup&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Pre-processing60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>4.01</p></td>
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
<td><p>BankGroup</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required in order to convert postal address data to the new logistics postal address model for 6.0. The location for \<c\>BankGroup\</c\> will be kept as a reference to \<c\>LogisticsLocation\</c\> record.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: BankGroup</p></th>
<th><p>To Table: LogisticsPostalAddress</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Address</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>CountryRegion</p></td>
<td><p>CountryRegionId</p></td>
</tr>
<tr class="odd">
<td><p>State</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>County</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>ZipCode</p></td>
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
<th><p>To Table: Shadow_BankGroup</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Location</p></td>
<td><p>Location</p></td>
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
<td><p>BankGroup</p></td>
<td><p>Location</p></td>
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
<td><p>BankGroup</p></td>
<td><p>Address</p></td>
</tr>
<tr class="even">
<td><p>BankGroup</p></td>
<td><p>CountryRegion</p></td>
</tr>
<tr class="odd">
<td><p>BankGroup</p></td>
<td><p>State</p></td>
</tr>
<tr class="even">
<td><p>BankGroup</p></td>
<td><p>County</p></td>
</tr>
<tr class="odd">
<td><p>BankGroup</p></td>
<td><p>ZipCode</p></td>
</tr>
<tr class="even">
<td><p>BankGroup</p></td>
<td><p>City</p></td>
</tr>
<tr class="odd">
<td><p>BankGroup</p></td>
<td><p>Street</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

