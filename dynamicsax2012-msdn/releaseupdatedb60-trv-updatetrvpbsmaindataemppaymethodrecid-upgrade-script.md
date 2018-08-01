---
title: ReleaseUpdateDB60_Trv.updateTrvPBSMaindataEmpPayMethodRecId Upgrade Script
TOCTitle: ReleaseUpdateDB60_Trv.updateTrvPBSMaindataEmpPayMethodRecId Upgrade Script
ms:assetid: 477f1125-eeaf-a618-856d-49045759c8a6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ718977(v=AX.60)
ms:contentKeyID: 49708009
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Trv.updateTrvPBSMaindataEmpPayMethodRecId Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Trv</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateTrvPBSMaindataEmpPayMethodRecId</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Populates the EmpPayMethodRecId field in the TrvPBSMaindata table, and a new foreign key field to the TrvEmpPayMethod table.</p></td>
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
<td><p>Expense management</p></td>
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
<td><p>TrvPBSMaindata</p></td>
</tr>
</tbody>
</table>


## Remarks

The TrvEmpPaymethod record is retrieved by using the worker and payment method combination. Then the EmpPayMethodRecId field is set by the last record ID from the TevEmpPaymethod table. The last record is selected because it is the most recent credit card for the employee.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: TrvEmpPaymethod</p></th>
<th><p>To Table: RecId</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TrvPBSMainData</p></td>
<td><p>EmpPayMethodRecId</p></td>
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
<td><p>TrvPBSMainData</p></td>
<td><p>EmpPayMethodRecId</p></td>
<td><p>RefRecId</p></td>
</tr>
</tbody>
</table>

  


