---
title: ReleaseUpdateDB63_HRMMinor.allowNoDupIndex Upgrade Script
TOCTitle: ReleaseUpdateDB63_HRMMinor.allowNoDupIndex Upgrade Script
ms:assetid: 507ea9a3-9c89-deb9-2c1b-0dbaf7e3180a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702733(v=AX.60)
ms:contentKeyID: 65236189
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB63\_HRMMinor.allowNoDupIndex Upgrade Script 


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB63_HRMMinor</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupIndex</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Resets the unique indexes on the HRM tables.</p></td>
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
<td><p>ReleaseUpdateDB63_HRMMinor</p></td>
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
<td><p>HCMPOSITIONFORECASTCOMPGROUPREFPOINT</p></td>
</tr>
<tr class="even">
<td><p>SYSINFOLOG</p></td>
</tr>
</tbody>
</table>


## Remarks

The unique \<c\>CompensationRateRefPointIdx\</c\> index of the \<c\>HcmPositionForecastCompGroupRefPoint\</c\> table is reset.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

