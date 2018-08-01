---
title: ReleaseUpdateDB60_Ledger.updateGDL_LJTransZakat_SA_Records Upgrade Script
TOCTitle: ReleaseUpdateDB60_Ledger.updateGDL_LJTransZakat_SA_Records Upgrade Script
ms:assetid: abb56447-72bb-fae5-0faf-d5b8f446adf0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686486(v=AX.60)
ms:contentKeyID: 49710441
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Ledger.updateGDL\_LJTransZakat\_SA\_Records Upgrade Script [AX 2012]


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
<td><p>updateGDL_LJTransZakat_SA_Records</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the surrogate key column in the foreign tables by using the value from the RecId field of the primary table.</p></td>
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
<td><p>VendInfoZakat_SA</p></td>
</tr>
<tr class="odd">
<td><p>LedgerJournalTransZakat_SA</p></td>
</tr>
</tbody>
</table>


## Remarks

Updates the AssetGroup field in the LedgerJournalTransZakat\_SA tables with the value from the RecId field in the AssetGroupZakat\_SA table. Updates the Subcontractor field in the LedgerJournalTransZakat\_SA table with the value from the RecId field in the VendInfoZakat\_SA table.

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

