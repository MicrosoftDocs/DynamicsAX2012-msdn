---
title: ReleaseUpdateDB60_Asset.updateLtAssetPackingSlip Upgrade Script
TOCTitle: ReleaseUpdateDB60_Asset.updateLtAssetPackingSlip Upgrade Script
ms:assetid: 208cfb62-0903-e30d-85bc-bb4be70cbab5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ684895(v=AX.60)
ms:contentKeyID: 49707097
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Asset.updateLtAssetPackingSlip Upgrade Script 


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
<td><p>updateLtAssetPackingSlip</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>This method updates the LtAssetPackingSlip and LtAssetPackingSlipLine tables.</p></td>
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
<td><p>LtAssetPackingSlip</p></td>
</tr>
<tr class="even">
<td><p>LtAssetPackingSlipLine</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the LtAssetPackingSlip surrogate key column based on the LtAssetPackingSlip table in the LtAssetPackingSlipLine table. Updates the LtAssetPackingSlipLine table by migrating the value of the responsible from and location from values from the LtAssetPackingSlip table as the information was moved from the header record to the line record. The DEL\_DepartmentFrom and DEL\_DepartmentTo columns are marked for deletion, however, they are not migrated. The reason is that the column is a different entity between Ax 2009 and Ax 2012, and during the update it is not possible to determine the intent of the column.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: LTAssetPackingSlip</p></th>
<th><p>To Table: LTAssetPackingSlipLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_ResponsibleFrom</p></td>
<td><p>ResponsibleFromId</p></td>
</tr>
<tr class="even">
<td><p>DEL_AssetLocationIdFrom</p></td>
<td><p>AssetLocationIdFrom</p></td>
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
<td><p>LTAssetPackingSlip</p></td>
<td><p>DEL_DepartmentFrom</p></td>
</tr>
<tr class="even">
<td><p>LTAssetPackingSlip</p></td>
<td><p>DEL_DepartmentTo</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

