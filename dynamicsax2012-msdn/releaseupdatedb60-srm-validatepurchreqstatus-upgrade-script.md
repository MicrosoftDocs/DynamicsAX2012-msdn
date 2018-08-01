---
title: ReleaseUpdateDB60_Srm.validatePurchReqStatus Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.validatePurchReqStatus Upgrade Script
ms:assetid: d91728c5-02eb-7e79-fb4d-01cee8bf3a2c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687108(v=AX.60)
ms:contentKeyID: 49711556
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.validatePurchReqStatus Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

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
<td><p>validatePurchReqStatus</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Validates whether the records in &lt;c&gt;PurchReqTable&lt;/c&gt; and &lt;c&gt;PurchReqLine&lt;/c&gt; are eligible for upgrade to this release.</p></td>
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


## Remarks

This release does not support in-flight upgrade of purchase requisitions. The purchase requisition must be in Draft status or greater than or equal to Approved status. This script throws an error if any purchase requisition is in un-supported status.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

