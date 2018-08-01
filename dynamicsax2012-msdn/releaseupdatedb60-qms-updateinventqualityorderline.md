---
title: ReleaseUpdateDB60_QMS.updateInventQualityOrderLine
TOCTitle: ReleaseUpdateDB60_QMS.updateInventQualityOrderLine
ms:assetid: 5b125699-ae80-d0f0-7a29-9303da6cc1cd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736303(v=AX.60)
ms:contentKeyID: 49708478
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_QMS.updateInventQualityOrderLine 


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
<td><p>updateInventQualityOrderLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Copies data from the QmmOrderLine table to the InventQualityOrderLine table.</p></td>
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
<td><p>DEL_QmmOrderLine</p></td>
</tr>
<tr class="even">
<td><p>InventQualityOrderLine</p></td>
</tr>
</tbody>
</table>


## Remarks

This script is set to be dependent on the ReleaseUpdateDB60\_Basic.updateUnitOfMeasureConsumers upgrade script that updates units of measure in all application tables. By doing this we ensure that mentioned script will be executed on the empty InventQualityOrderLine table. Units of measure for the InventQualityOrderLine table will be updated after by the ReleaseUpdateDB60\_QMS.updateUnitOfMeasureQMSConsumers upgrade script.

  


