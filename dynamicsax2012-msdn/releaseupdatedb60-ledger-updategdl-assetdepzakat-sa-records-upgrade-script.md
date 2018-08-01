---
title: ReleaseUpdateDB60_Ledger.updateGDL_AssetDepZakat_SA_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_AssetDepZakat_SA_Records Upgrade Script
ms:assetid: 1a51da6a-1f8b-48a9-ddc3-fd905607f500
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718649(v=AX.60)
ms:contentKeyID: 49706926
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_AssetDepZakat\_SA\_Records Upgrade Script 


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
<td><p>updateGDL_AssetDepZakat_SA_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the AssetGroup field in the AssetDepreciationZakat_SA table with the value from the RecId field of the AssetGroupZakat_SA table.</p></td>
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
<td><p>AssetGroupZakat_SA</p></td>
</tr>
<tr class="even">
<td><p>AssetDepreciationZakat_SA</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the AssetGroup field in the AssetDepreciationZakat\_SA table with the value from the RecId field in the AssetGroupZakat\_SA table.

  


