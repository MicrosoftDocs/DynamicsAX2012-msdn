---
title: ReleaseUpdateDB60_Jmg.updateJmgIpcActivity Upgrade Script
TOCTitle: ReleaseUpdateDB60_Jmg.updateJmgIpcActivity Upgrade Script
ms:assetid: 06ce7e02-a843-91af-b5ad-07a914613165
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684751(v=AX.60)
ms:contentKeyID: 49706447
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Jmg.updateJmgIpcActivity Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Jmg</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateJmgIpcActivity</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the DefaultDimension, the LedgerDimension, and OffsetLedgerDimension fields of the JmgIpcActivity table with the corresponding value from the RecId field of the DimensionAttributeValueSet table and the DimensionAttributeValueCombination table.</p></td>
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
<td><p>Production</p></td>
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
<td><p>JmgIpcActivity</p></td>
</tr>
</tbody>
</table>


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
<td><p>JmgIpcActivity</p></td>
<td><p>DefaultDimension</p></td>
<td><p>DimensionDefault</p></td>
</tr>
<tr class="even">
<td><p>JmgIpcActivity</p></td>
<td><p>LedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
</tr>
<tr class="odd">
<td><p>JmgIpcActivity</p></td>
<td><p>OffsetLedgerDimension</p></td>
<td><p>LedgerDimensionAccount</p></td>
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
<td><p>JmgIpcActivity</p></td>
<td><p>Dimension</p></td>
</tr>
<tr class="even">
<td><p>JmgIpcActivity</p></td>
<td><p>LedgerAccountNum</p></td>
</tr>
<tr class="odd">
<td><p>JmgIpcActivity</p></td>
<td><p>OffsetLedgerAccountNum</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

