---
title: ReleaseUpdateDB60_Srm.updatePurchReqLineUnitOfMeasure Upgrade Script
TOCTitle: ReleaseUpdateDB60_Srm.updatePurchReqLineUnitOfMeasure Upgrade Script
ms:assetid: 7c87264d-9cb5-1f82-95b1-0dac2f521639
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719465(v=AX.60)
ms:contentKeyID: 49709255
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Srm.updatePurchReqLineUnitOfMeasure Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Srm</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePurchReqLineUnitOfMeasure</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Responsible for handling upgrade of the references to the UnitOfMeasure table changing them to use the UnitOfMeasure primary key instead of natural key.</p></td>
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
<td><p>SRM</p></td>
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
<td><p>PurchReqLine</p></td>
</tr>
</tbody>
</table>


## Remarks

The string PurchUnit and ProjSalesUnitId fields have been renamed to “DEL\_PurchUnit”, “DEL\_ ProjSalesUnitId” respectively, replaced with RefRecId fields with the PurchUnitOfMeasure, ProjSalesUnitOfMeasure.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: PurchReqLine</p></th>
<th><p>To Table: PurchReqLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DEL_PurchUnit</p></td>
<td><p>PurchUnitOfMeasure</p></td>
</tr>
<tr class="even">
<td><p>DEL_ ProjSalesUnitId</p></td>
<td><p>ProjSalesUnitOfMeasure</p></td>
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
<td><p>PurchReqLine</p></td>
<td><p>PurchUnitOfMeasure</p></td>
<td><p>RefRecId</p></td>
</tr>
<tr class="even">
<td><p>PurchReqLine</p></td>
<td><p>ProjSalesUnitOfMeasure</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>


## Name Changes for Tables or Fields

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Old Table Name: PurcReqLine</p></th>
<th><p>New Table Name: PurchReqLine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Old Field Name:</p></td>
<td><p>New Field Name:</p></td>
</tr>
<tr class="even">
<td><p>PurchUnit</p></td>
<td><p>DEL_PurchUnit</p></td>
</tr>
<tr class="odd">
<td><p>ProjSalesUnitId</p></td>
<td><p>DEL_ ProjSalesUnitId</p></td>
</tr>
</tbody>
</table>

  


