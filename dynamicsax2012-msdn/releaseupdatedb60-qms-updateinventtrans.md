---
title: ReleaseUpdateDB60_QMS.updateInventTrans
TOCTitle: ReleaseUpdateDB60_QMS.updateInventTrans
ms:assetid: 36adff36-02f5-bb70-c8cb-93fa5195907a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685171(v=AX.60)
ms:contentKeyID: 49707625
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_QMS.updateInventTrans 


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
<td><p>updateInventTrans</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the InventTrans records that are related to the quality management solution.</p></td>
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
<td><p>InventQualityOrderTable</p></td>
</tr>
<tr class="even">
<td><p>InventTrans</p></td>
</tr>
<tr class="odd">
<td><p>DataArea</p></td>
</tr>
</tbody>
</table>


## Remarks

All transactions with the QmmScrapped status issue should be updated. The QmmScrapped status issue has been removed and will be replaced with the Sold status. These transactions should also have the relation changed from referencing a purchase order to instead referencing the quality order directly. This means that the QmmOrderIdRef status issue will be removed from the InventTrans table and the content will be moved to the TransRefId field. The TransType field will get the new QualityOrder value and the inventTransId field will get the value from the quality order.

  


