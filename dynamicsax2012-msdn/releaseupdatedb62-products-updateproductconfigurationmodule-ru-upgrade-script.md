﻿---
title: ReleaseUpdateDB62_Products.updateProductConfigurationModule_RU Upgrade Script
TOCTitle: ReleaseUpdateDB62_Products.updateProductConfigurationModule_RU Upgrade Script
ms:assetid: 8f60f1ba-ed78-5ccc-55f7-1faff0abe745
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702783(v=AX.60)
ms:contentKeyID: 65236238
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Products.updateProductConfigurationModule\_RU Upgrade Script [AX 2012]


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB62_Products</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateProductConfigurationModule_RU</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Product configuration module to support owner ID, profile ID, and GTD ID.</p></td>
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
<td><p>Product management</p></td>
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
<td><p>PCTEMPLATEATTRIBUTE</p></td>
</tr>
<tr class="even">
<td><p>PCTEMPLATE</p></td>
</tr>
</tbody>
</table>


## Remarks

Entries for InventOwnerId\_RU, InventGTDId\_RU, and InventProfileId\_RU are added to the \<c\>PCTemplateAttribute\</c\> table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

