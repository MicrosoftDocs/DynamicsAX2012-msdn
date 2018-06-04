---
title: ReleaseUpdateDB60_EcoRes.createEcoResProductMasterStyle Upgrade Script
TOCTitle: ReleaseUpdateDB60_EcoRes.createEcoResProductMasterStyle Upgrade Script
ms:assetid: 74defbdc-3c0a-b0a1-0513-dd8158216ec2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719295(v=AX.60)
ms:contentKeyID: 49709087
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_EcoRes.createEcoResProductMasterStyle Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_EcoRes</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>createEcoResProductMasterStyle</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the EcoResProductMasterStyle table with information from the RetailInventStyle table through the DEL_EcoResProdUpgradeStyle table.</p></td>
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
<td><p>ECORESPRODUCTMASTERSTYLE</p></td>
</tr>
<tr class="even">
<td><p>DEL_ECORESPRODUPGRADESTYLE</p></td>
</tr>
<tr class="odd">
<td><p>DEL_ECORESPRODUPGRADEPRODUCT</p></td>
</tr>
<tr class="even">
<td><p>ECORESPRODUCTDIMENSIONATTRIBUTE</p></td>
</tr>
<tr class="odd">
<td><p>ECORESPRODUCTMASTER</p></td>
</tr>
<tr class="even">
<td><p>ECORESPRODUCTMASTERDIMENSIONVALUE</p></td>
</tr>
<tr class="odd">
<td><p>ECORESSTYLE</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

