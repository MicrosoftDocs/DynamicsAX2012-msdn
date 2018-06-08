---
title: ReleaseUpdateDB62_Products.updateProductConfigurationModule Upgrade Script
TOCTitle: ReleaseUpdateDB62_Products.updateProductConfigurationModule Upgrade Script
ms:assetid: 1d41f20a-8b77-ea4b-8fd0-396384198c16
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn975042(v=AX.60)
ms:contentKeyID: 65236156
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_Products.updateProductConfigurationModule Upgrade Script 


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
<td><p>updateProductConfigurationModule</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Product configuration module to support inventory status and license plate.</p></td>
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

Entries for InventStatusId and LicensePlateId are added to the table \<c\>PCTemplateAttribute\</c\>.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

