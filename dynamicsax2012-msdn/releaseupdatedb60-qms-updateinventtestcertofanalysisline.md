---
title: ReleaseUpdateDB60_QMS.updateInventTestCertOfAnalysisLine
TOCTitle: ReleaseUpdateDB60_QMS.updateInventTestCertOfAnalysisLine
ms:assetid: 724b2f60-43d9-6032-6cea-5f551ca16021
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685801(v=AX.60)
ms:contentKeyID: 49709002
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_QMS.updateInventTestCertOfAnalysisLine 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_QMS</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateInventTestCertOfAnalysisLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the QmmCertOfAnalysisLine table to the InventTestCertOfAnalysisLine table.</p></td>
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
<td><p>Quality Management System</p></td>
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
<td><p>DEL_QmmCertOfAnalysisLine</p></td>
</tr>
<tr class="even">
<td><p>InventTestCertOfAnalysisLine</p></td>
</tr>
</tbody>
</table>


## Remarks

This script is set to be dependent on the ReleaseUpdateDB60\_Basic.updateUnitOfMeasureConsumers upgrade script that updates the units of measure in all application tables. By doing this we ensure that the script will be executed on the empty InventTestCertOfAnalysisLine table. Units of measure for the InventTestCertOfAnalysisLine table will be updated after by the ReleaseUpdateDB60\_QMS.updateUnitOfMeasureQMSConsumers upgrade script.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

