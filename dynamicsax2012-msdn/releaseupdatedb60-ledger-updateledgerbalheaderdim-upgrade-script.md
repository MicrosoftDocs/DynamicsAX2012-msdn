---
title: ReleaseUpdateDB60_Ledger.updateLedgerBalHeaderDim Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateLedgerBalHeaderDim Upgrade Script
ms:assetid: b4e3637e-120f-8546-e31d-df813283d2e1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736985(v=AX.60)
ms:contentKeyID: 49710669
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateLedgerBalHeaderDim Upgrade Script 


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
<td><p>updateLedgerBalHeaderDim</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the MainFocusHierarchy and SecondaryFocusHierarchy fields in the LedgerBalHeaderDim table.</p></td>
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
<td><p>LedgerBalHeaderDim</p></td>
</tr>
</tbody>
</table>


## Remarks

Sets the value of the MainFocusHierarchy and SecondaryFocusHierarchy fields to the RecId field of the DimensionHierarchy table that correspond to the del\_MainFocus and del\_SecondaryFocus tables respectively.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LedgerBalHeaderDim</p></th>
<th><p>To Table: LedgerBalHeaderDim</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>del_MainFocus</p></td>
<td><p>MainFocusHierarchy</p></td>
</tr>
<tr class="even">
<td><p>del_SecondaryFocus</p></td>
<td><p>SecondaryFocusHierarchy</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

