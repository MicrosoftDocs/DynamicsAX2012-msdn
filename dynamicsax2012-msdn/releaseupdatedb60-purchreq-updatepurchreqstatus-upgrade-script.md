---
title: ReleaseUpdateDB60_PurchReq.updatePurchReqStatus Upgrade Script
TOCTitle: ReleaseUpdateDB60_PurchReq.updatePurchReqStatus Upgrade Script
ms:assetid: ece0e47e-9b17-2989-53d2-a2c7e5b0c343
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719927(v=AX.60)
ms:contentKeyID: 49711998
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PurchReq.updatePurchReqStatus Upgrade Script 


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
<td><p>updatePurchReqStatus</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>The value of new Status field is initialized from the new Status field.</p></td>
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

In this release we have introduced a new Status field, which inherits from the PurchReqRequisitionStatus enumeration type. This script initializes the value of a new Status field from the old Status field.

## New Tables or Fields

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
<th><p>Extended Data Type</p>
<p>-or- Base Enum</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchReqTable</p></td>
<td><p>Status</p></td>
<td><p>PurchReqRequisitionStatus</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

