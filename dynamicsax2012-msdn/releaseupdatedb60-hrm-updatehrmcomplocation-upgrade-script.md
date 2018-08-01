---
title: ReleaseUpdateDB60_HRM.updateHRMCompLocation Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMCompLocation Upgrade Script
ms:assetid: cfd9d1e8-3ad2-b8a5-779e-210340f32d62
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686892(v=AX.60)
ms:contentKeyID: 49711341
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMCompLocation Upgrade Script 


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
<td><p>updateHRMCompLocation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Location field of the HRMCompLocation table.</p></td>
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
<td><p>LogisticsAddressZipCode</p></td>
</tr>
<tr class="even">
<td><p>LogisticsAddresssCity</p></td>
</tr>
<tr class="odd">
<td><p>HRMCompLocation</p></td>
</tr>
<tr class="even">
<td><p>LogisticsLocation</p></td>
</tr>
<tr class="odd">
<td><p>LogisticsPostalAddress</p></td>
</tr>
</tbody>
</table>


## Remarks

Creates a new record in the LogisticsLocation and the LogisticsPostalAddress table based on address information in the HRMCompLocation table. Updates the Location field of the HRMCompLocation table with the corresponding value of the RecId field of the LogisticsLocation table.

  


