---
title: ReleaseUpdateDB60_Asset.updateAssetInternalTransferHistory Upgrade Script
TOCTitle: ReleaseUpdateDB60_Asset.updateAssetInternalTransferHistory Upgrade Script
ms:assetid: d7788d72-4c6d-8f40-5fe9-2906c4bd09a7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ687073(v=AX.60)
ms:contentKeyID: 49711521
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Asset.updateAssetInternalTransferHistory Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Asset</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateAssetInternalTransferHistory</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the AssetInternalTransferHistory table. The AssetInternalTransferHistory table keeps the history of changes made to an asset location and department.</p></td>
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
<td><p>Fixed Asset</p></td>
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
<td><p>AssetInternalTransferHistory</p></td>
</tr>
</tbody>
</table>


## Remarks

In the previous version, this history was tracked by posting FA journal transactions of type internal transfer. In AX6, these are no longer posted to the FA journal and instead tracked by the AssetInternalTransferHistory table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AssetTrans</p></th>
<th><p>To Table: AssetInternalTransferHistory</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AssetId</p></td>
<td><p>AssetId</p></td>
</tr>
<tr class="even">
<td><p>transDate</p></td>
<td><p>TranserDate</p></td>
</tr>
<tr class="odd">
<td><p>DEL_Location_LV</p></td>
<td><p>ToLocation</p></td>
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
<td><p>AssetInternalTransferHistory</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

