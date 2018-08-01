---
title: ReleaseUpdateTransformDB40_Proj.projProposalOnAccPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB40_Proj.projProposalOnAccPreUpgradeProcess Upgrade Script
ms:assetid: f363861b-0ca3-2a6c-7f71-66993608b362
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ737512(v=AX.60)
ms:contentKeyID: 49712206
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB40\_Proj.projProposalOnAccPreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB40_Proj</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>projProposalOnAccPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Upgrades the &lt;c&gt;ServiceTariffId_PL&lt;/c&gt; field in &lt;c&gt;ProjProposalOnAcc&lt;/c&gt; table.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Live</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
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
<td><p>ProjProposalOnAcc</p></td>
</tr>
</tbody>
</table>


## Remarks

The field service tariff id is deleted from the \<c\>ProjProposalOnAcc\</c\> table in 6.2. A reference to the \<c\>ProjProposalOnAcc\</c\> record and corresponding reference to \<c\>ServiceTariffNumber\_PL\</c\> record is added in the new table \<c\>TaxServiceTariff\</c\>.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjProposalOnAcc</p></th>
<th><p>To Table: TaxServiceTariff</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ParentRecId</p></td>
</tr>
<tr class="even">
<td><p>TableId</p></td>
<td><p>ParentTableId</p></td>
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
<td><p>ProjProposalOnAcc</p></td>
<td><p>ServiceTariffId_PL</p></td>
</tr>
</tbody>
</table>

  


