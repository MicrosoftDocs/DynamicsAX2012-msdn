---
title: ReleaseUpdateDB62_HRMMinor.updateHcmPositionForecastLastModified Upgrade Script
TOCTitle: ReleaseUpdateDB62_HRMMinor.updateHcmPositionForecastLastModified Upgrade Script
ms:assetid: 888b2855-ff51-829a-088b-e5648d94aa0a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn702780(v=AX.60)
ms:contentKeyID: 65236235
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB62\_HRMMinor.updateHcmPositionForecastLastModified Upgrade Script 


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB62_HRMMinor</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateHcmPositionForecastLastModified</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies &lt;c&gt;HcmPositionForecastLastModified&lt;/c&gt; record and links it to the &lt;c&gt;HcmPositionForecastScenario&lt;/c&gt; After copying and linking the records, deletes the records with a blank &lt;c&gt;PositionForecastScenario&lt;/c&gt; value.</p></td>
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
<td><p>HRM</p></td>
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
<td><p>HCMPOSITIONFORECASTLASTMODIFIED</p></td>
</tr>
<tr class="even">
<td><p>HCMPOSITIONFORECASTSCENARIO</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

