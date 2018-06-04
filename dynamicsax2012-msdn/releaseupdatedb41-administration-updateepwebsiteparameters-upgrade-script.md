---
title: ReleaseUpdateDB41_Administration.updateEPWebSiteParameters Upgrade Script
TOCTitle: ReleaseUpdateDB41_Administration.updateEPWebSiteParameters Upgrade Script
ms:assetid: d596dacf-0ed9-05a2-071c-226856df58ed
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687028(v=AX.60)
ms:contentKeyID: 49711476
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB41\_Administration.updateEPWebSiteParameters Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB41_Administration</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateEPWebSiteParameters</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This function copies data from the DEL_WebSite and DEL_EPParameters table to the EPWebSiteParameters table.</p></td>
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
<td><p>Administration</p></td>
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
<td><p>EPWebSiteParameters</p></td>
</tr>
<tr class="even">
<td><p>DEL_WebSite</p></td>
</tr>
<tr class="odd">
<td><p>DEL_EPParameters</p></td>
</tr>
</tbody>
</table>


## Remarks

The DEL\_WebSite has many company specific rows. The DEL\_EPParameters has one row per company. The EPWebSiteParameters has many company neutral rows. The data from the DEL\_WebSite table will be copied directly into the EPWebSiteParameters table and specific fields from the DEL\_EPPParameters table will be duplicated across each entry. The EPWebSiteParameters table has the new CompanyIndependent field. This field indicates whether a website is associated with a company. The DEL\_WebSite has the CompanyId field that contains the company ID of the company that the website belongs. As such, this field should never be empty and the CompanyIndependent will be set to No for all data that is transferred. Transfer all fields from the DEL\_Website table. Transfer the EnableEncryption, EncryptionExpirationInterval, ImageResize, ImageSizeSmall, ImageSizeLarge, and ImageRatiomation fields from the DEL\_EPParameters table.

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
<td><p>EPWebSiteParameters</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
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
<td><p>DEL_EPParameters</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>DEL_WebSite</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

