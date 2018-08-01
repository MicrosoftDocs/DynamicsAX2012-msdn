---
title: ReleaseUpdateDB60_HRM.updateHRMCourseLocation Upgrade Script
TOCTitle: ReleaseUpdateDB60_HRM.updateHRMCourseLocation Upgrade Script
ms:assetid: fa6c33db-5fb4-37e5-e669-9c625b95f45e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720059(v=AX.60)
ms:contentKeyID: 49712365
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_HRM.updateHRMCourseLocation Upgrade Script 


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
<td><p>updateHRMCourseLocation</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the Location field of the HRMCourseLocation table.</p></td>
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
<td><p>HRMCourseLocation</p></td>
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

Creates a new record in the LogisticsLocation table and the LogisticsPostalAddress table based on address information in the HRMCourseLocation table. Updates the Location field of the HRMCourseLocation table with the corresponding value of the RecId field of the LogisticsLocation table.

  


