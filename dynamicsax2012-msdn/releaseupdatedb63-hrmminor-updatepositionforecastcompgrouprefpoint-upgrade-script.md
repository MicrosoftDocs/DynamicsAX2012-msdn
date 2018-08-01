---
title: ReleaseUpdateDB63_HRMMinor.updatePositionForecastCompGroupRefPoint Upgrade Script
TOCTitle: ReleaseUpdateDB63_HRMMinor.updatePositionForecastCompGroupRefPoint Upgrade Script
ms:assetid: 5d6d9579-5875-cc0b-716b-2ecd8e835b20
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702743(v=AX.60)
ms:contentKeyID: 65236199
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB63\_HRMMinor.updatePositionForecastCompGroupRefPoint Upgrade Script [AX 2012]


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
<td><p>updatePositionForecastCompGroupRefPoint</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates &lt;c&gt;HcmPositionForecastCompGroupRefPoint&lt;/c&gt; table records with &lt;c&gt;HcmPositionForecastCompensationRate&lt;/c&gt; table records.</p></td>
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
<td><p>HCMPOSITIONFORECASTCOMPENSATIONRATE</p></td>
</tr>
<tr class="odd">
<td><p>HCMPOSITIONFORECASTCOMPENSATIONGROUP</p></td>
</tr>
</tbody>
</table>


## Remarks

The \<c\>compensationRate\</c\> field on the \<c\>HcmPositionForecastCompGroupRefPoint\</c\> table is set with the RecId from the \<c\>HcmPositionForecastCompensationRate\</c\> table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

