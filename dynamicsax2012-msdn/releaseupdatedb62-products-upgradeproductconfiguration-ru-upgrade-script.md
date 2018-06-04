---
title: ReleaseUpdateDB62_Products.upgradeProductConfiguration_RU Upgrade Script
TOCTitle: ReleaseUpdateDB62_Products.upgradeProductConfiguration_RU Upgrade Script
ms:assetid: f90d600d-4205-65b0-8cdb-761872e4bc27
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702836(v=AX.60)
ms:contentKeyID: 65236291
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Products.upgradeProductConfiguration\_RU Upgrade Script 


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
<td><p>upgradeProductConfiguration_RU</p></td>
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

Entries for InventOwnerId\_RU, InventGTDId\_RU, and InventProfileId\_RU are added to the \<c\>PCTemplateAttribute\</c\> table. The entries might have been added to the table already and if this is the case, nothing is added.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

