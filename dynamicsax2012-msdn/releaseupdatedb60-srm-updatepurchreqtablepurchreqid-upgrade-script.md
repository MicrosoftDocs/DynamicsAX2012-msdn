---
title: ReleaseUpdateDB60_Srm.updatePurchReqTablePurchReqId Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.updatePurchReqTablePurchReqId Upgrade Script
ms:assetid: 253b4e46-5d5a-eb64-4adb-e85813aeb3de
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ685021(v=AX.60)
ms:contentKeyID: 49707221
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.updatePurchReqTablePurchReqId Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Srm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePurchReqTablePurchReqId</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Appends the PurchReqId field in the PurchReqTable table with the value in the DEL_DataArea field.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>PurchReqTable</p></td>
</tr>
</tbody>
</table>


## Remarks

The saveDataPerCompany property of the PurchReqTable table has been set to the no value in this release. In order to preserve uniqueness, this method appends the PurchReqId field in the PurchReqTable table with the value in the DEL\_DataArea field.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

