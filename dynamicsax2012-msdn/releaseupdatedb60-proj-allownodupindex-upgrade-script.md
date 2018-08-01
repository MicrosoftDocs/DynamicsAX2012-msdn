---
title: ReleaseUpdateDB60_Proj.allowNoDupIndex Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.allowNoDupIndex Upgrade Script
ms:assetid: b5928215-cfcc-501a-74e4-1d0cd78824f3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736991(v=AX.60)
ms:contentKeyID: 49710675
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.allowNoDupIndex Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>allowNoDupIndex</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Reset the unique indexes in the project accounting tables.</p></td>
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
<td><p>Project</p></td>
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
<td><p>ProjCostPriceExpense</p></td>
</tr>
<tr class="even">
<td><p>ProjCostSalesPrice</p></td>
</tr>
<tr class="odd">
<td><p>ProjDefaultOffsetSetup</p></td>
</tr>
<tr class="even">
<td><p>ProjHourCostPrice</p></td>
</tr>
<tr class="odd">
<td><p>ProjHourSalesPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjPeriodEmpl</p></td>
</tr>
<tr class="odd">
<td><p>ProjRevenueSalesPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjValEmplCategorySetUp</p></td>
</tr>
<tr class="odd">
<td><p>ProjValEmplProjSetup</p></td>
</tr>
<tr class="even">
<td><p>SyncProjTransaction</p></td>
</tr>
</tbody>
</table>


## Remarks

The ProjEmplCatDateIdx unique index of the ProjCostPriceExpense table is reset. The ProjCatEmplDateIdx unique index of the ProjCostSalesPrice table is reset. The DefaultOffsetAccountIndex unique index of the ProjDefaultOffsetSetup table is reset. The ProjEmplCatDateIdx unique index of the ProjHourCostPrice table is reset. The ProjCatEmplDateIdx unique index of the ProjHourSalesPrice table is reset. The PeriodIdIdx unique index of the ProjPeriodEmpl table is reset. The rojCatEmplDateIdx unique index of the ProjRevenueSalesPrice table is reset. The GroupEmplIdx unique index of the ProjValEmplCategorySetUp table is reset. The GroupProjIdx unique index of the ProjValEmplProjSetup table is reset. The HcmWorkerIdx unique index of the ProjExpPolicyGroupEmpl table is reset. The Idx unique index of the TSTimesheetEmployeeFilter table is reset. The SyncProjTransIdx unique index of the SyncProjTransaction table is reset.

  


