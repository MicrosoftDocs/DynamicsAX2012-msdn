﻿---
title: ReleaseUpdateDB60_Ledger.updateLedgerRowDefLine Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerRowDefLine Upgrade Script
ms:assetid: b2248678-ddb4-125a-cf34-8dd284e25c7f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736903(v=AX.60)
ms:contentKeyID: 49710587
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerRowDefLine Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Ledger</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateLedgerRowDefLine</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the DimensionAttribute and DimensionValueCriteria fields in the LedgerRowDefLine table.</p></td>
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
<td><p>General ledger</p></td>
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
<td><p>LedgerRowDefLine</p></td>
</tr>
</tbody>
</table>


## Remarks

Sets the DimensionAttribute field to the record ID of the DimensionAttribute record that corresponds to the Priority field. The DimensionValueCriteria field is set to the AccountCriteria or del\_DimensionCriteria field values.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

