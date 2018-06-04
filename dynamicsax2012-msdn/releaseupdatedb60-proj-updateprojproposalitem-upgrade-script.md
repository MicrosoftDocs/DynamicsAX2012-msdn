---
title: ReleaseUpdateDB60_Proj.updateProjProposalItem Upgrade Script
TOCTitle: ReleaseUpdateDB60_Proj.updateProjProposalItem Upgrade Script
ms:assetid: af87b6c2-9c16-1137-b2eb-9b7412449fd8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686570(v=AX.60)
ms:contentKeyID: 49710524
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Proj.updateProjProposalItem Upgrade Script 


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
<td><p>updateProjProposalItem</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the new transaction invoice detail table.</p></td>
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
<td><p>ProjProposalItem</p></td>
</tr>
<tr class="even">
<td><p>ProjProposalItemDetail</p></td>
</tr>
</tbody>
</table>


## Remarks

A project transaction can now be billed to multiple customers. To support split billing, another level of tables was created. The sales amounts for billing hour transactions will be stored in the new ProjProposalItemDetail table. This new table is related to the existing ProjProposalItem table.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjProposalItem</p></th>
<th><p>To Table: ProjProposalItemDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>ProposalRefRecId</p></td>
</tr>
<tr class="even">
<td><p>DEL_SalesPrice</p></td>
<td><p>SalesPrice</p></td>
</tr>
<tr class="odd">
<td><p>DEL_LineAmount</p></td>
<td><p>LineAmount</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ProjItemTransSale</p></th>
<th><p>To Table: ProjProposalItemDetail</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>SaleRefRecId</p></td>
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
<td><p>ProjProposalItemDetail</p></td>
<td><p></p></td>
<td><p></p></td>
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
<td><p>ProjProposalItem</p></td>
<td><p>DEL_SalesPrice</p></td>
</tr>
<tr class="even">
<td><p>ProjProposalItem</p></td>
<td><p>DEL_LineAmount</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

