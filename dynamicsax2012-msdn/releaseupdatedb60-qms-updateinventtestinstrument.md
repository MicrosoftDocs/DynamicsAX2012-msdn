---
title: ReleaseUpdateDB60_QMS.updateInventTestInstrument
TOCTitle: ReleaseUpdateDB60_QMS.updateInventTestInstrument
ms:assetid: 2b6ad64e-d755-3b86-0252-668de2de3792
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ735948(v=AX.60)
ms:contentKeyID: 49707365
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_QMS.updateInventTestInstrument [AX 2012]


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
<td><p>updateInventTestInstrument</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the QmmTestTool table to the InventTestInstrument table.</p></td>
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
<td><p>DEL_QmmTestTool</p></td>
</tr>
<tr class="even">
<td><p>InventTestInstrument</p></td>
</tr>
</tbody>
</table>


## Remarks

This script is set to be dependent on the ReleaseUpdateDB60\_Basic.updateUnitOfMeasureConsumers upgrade script that updates units of measure in all application tables. By doing this we ensure that script will be executed on the empty InventTestInstrument table. Units of measure for the InventTestInstrument table will be updated afterwards by the ReleaseUpdateDB60\_QMS.updateUnitOfMeasureQMSConsumers upgrade script.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

