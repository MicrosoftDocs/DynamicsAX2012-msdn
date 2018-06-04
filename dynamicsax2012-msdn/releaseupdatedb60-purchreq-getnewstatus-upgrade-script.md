---
title: ReleaseUpdateDB60_PurchReq.GetNewStatus Upgrade Script
TOCTitle: ReleaseUpdateDB60_PurchReq.GetNewStatus Upgrade Script
ms:assetid: fea483d0-5674-1ef6-1fa6-1541e00cc8f7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ720193(v=AX.60)
ms:contentKeyID: 49712498
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_PurchReq.GetNewStatus Upgrade Script 


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
<td><p>GetNewStatus</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Maps the value of the requisition status from AX 2009 to the requisition status in this release.</p></td>
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

This mapping is for the upgrade of the relevant fields in the PurchReqTable table and the PurchReqLine table.

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
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>Status</p></td>
<td><p>PurchReqRequisitionStatus</p></td>
</tr>
</tbody>
</table>


## Deleted Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table</p></th>
<th><p>Field</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchReqTable</p></td>
<td><p>Status</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>Status</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

