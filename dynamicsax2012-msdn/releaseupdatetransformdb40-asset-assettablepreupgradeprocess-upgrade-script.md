---
title: ReleaseUpdateTransformDB40_Asset.assetTablePreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Asset.assetTablePreUpgradeProcess Upgrade Script
ms:assetid: 4601b6ae-e3e5-6d79-d5ef-69239ca1bebd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718949(v=AX.60)
ms:contentKeyID: 49707983
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Asset.assetTablePreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Asset</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>assetTablePreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the WorkerResponsible field in the AssetTable table with the record ID of either user from the sysCompanyUserInfo table or worker from the HcmWorker table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft Dynamics AX Source</strong></p></td>
<td><p>Microsoft Dynamics AX 4.0</p></td>
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
<td><p>AssetTable</p></td>
</tr>
</tbody>
</table>


## Remarks

This upgrade is required to convert the account and dimension data to the new accounts and dimension model for Microsoft Dynamics AX 2012.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: AssetTable</p></th>
<th><p>To Table: Shadow_AssetTable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimension</p></td>
<td><p>DefaultDimesion</p></td>
</tr>
</tbody>
</table>

  


