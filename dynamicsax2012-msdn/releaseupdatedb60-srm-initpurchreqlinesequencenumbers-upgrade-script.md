---
title: ReleaseUpdateDB60_Srm.initPurchReqLineSequenceNumbers Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.initPurchReqLineSequenceNumbers Upgrade Script
ms:assetid: 1bb54686-6fbe-5734-9b2d-044764db0a62
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718686(v=AX.60)
ms:contentKeyID: 49706970
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.initPurchReqLineSequenceNumbers Upgrade Script 


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
<td><p>initPurchReqLineSequenceNumbers</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates an integer sequence number for the PurchReqLine table that is used for sorting.</p></td>
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
<td><p>Accounts payable</p></td>
</tr>
<tr class="even">
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
<td><p>PurchReqLine</p></td>
</tr>
</tbody>
</table>


## Remarks

The SequenceNumber fields are updated in the PurchReqLine table while the Purchase Requisition is in draft mode. Lines that are deleted after it is submitted will not be resequenced.

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
<td><p>PurchReqLine</p></td>
<td><p>SequenceNumber</p></td>
<td><p>SequenceNumber</p></td>
</tr>
</tbody>
</table>

  


