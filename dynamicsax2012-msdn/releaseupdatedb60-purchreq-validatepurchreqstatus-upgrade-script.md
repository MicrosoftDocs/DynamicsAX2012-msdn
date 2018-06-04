---
title: ReleaseUpdateDB60_PurchReq.validatePurchReqStatus Upgrade Script
TOCTitle: ReleaseUpdateDB60_PurchReq.validatePurchReqStatus Upgrade Script
ms:assetid: 61e3ff16-9793-7ef2-865a-7b7a955eb67d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719089(v=AX.60)
ms:contentKeyID: 49708629
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PurchReq.validatePurchReqStatus Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_PurchReq</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>validatePurchReqStatus</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates and throws errors if any purchase requisition has values in the status field that are not supported during the upgrade to this release.</p></td>
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
<tr class="even">
<td><p>PurchReqLine</p></td>
</tr>
</tbody>
</table>


## Remarks

The purchase requisition upgrade path to this release does not support the upgrade of in-flight requisitions. This script validates that all requisitions are either in Draft status or the status is greater than or equal to the Approved status.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

