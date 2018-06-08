---
title: ReleaseUpdateDB60_Basic.updateExpression Upgrade Script
TOCTitle: ReleaseUpdateDB60_Basic.updateExpression Upgrade Script
ms:assetid: 538fa6df-466f-d210-5c32-f0283749f3f8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ736109(v=AX.60)
ms:contentKeyID: 49708287
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Basic.updateExpression Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Basic</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updateExpression</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Moves metadata and data stored in the ExpressionDefinition and Projection fields into new tables. Validates each condition and then copies all invalid conditions into the ExpressionStaging table.</p></td>
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
<td><p>Basic</p></td>
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
<td><p>ExpressionTable</p></td>
</tr>
</tbody>
</table>


## Remarks

Expressions in Microsoft Dynamics AX 2012 have undergone data model changes in which the actual expression represented as XML strings in the ExpressionDefinition and Projection fields has been normalized into various tables. Information that was represented in the Projection column is now in the ExpressionProjectionDatasource and ExpressionProjectionField tables. Information represented in the ExpressionDefinition column is now in the ExpressionElement and ExpressionPredicate tables. The Projection and ExpressionDefinition columns have been deleted from the ExpressionTable table. A new table named the ExpressionStagingTable table has been introduced that will hold all invalid expressions after the upgrade is complete. Expressions that were created in Microsoft Dynamics AX 2009 may be invalid because metadata that was represented in the expressions may have changed. That is, fields have been renamed or moved, extended data types have changed, and so on.

## Data Migration Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>From Table: ExpressionTable</p></th>
<th><p>To Table: ExpressionProjectionDatasource</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Projection</p></td>
<td><p>ParentDatasource</p></td>
</tr>
<tr class="even">
<td><p>Projection</p></td>
<td><p>Name</p></td>
</tr>
<tr class="odd">
<td><p>Projection</p></td>
<td><p>Type</p></td>
</tr>
<tr class="even">
<td><p>Projection</p></td>
<td><p>DisplayName</p></td>
</tr>
<tr class="odd">
<td><p>Projection</p></td>
<td><p>TableName</p></td>
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
<th><p>From Table: ExpressionTable</p></th>
<th><p>To Table: ExpressionProjectionField</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Projection</p></td>
<td><p>Name</p></td>
</tr>
<tr class="even">
<td><p>Projection</p></td>
<td><p>Category</p></td>
</tr>
<tr class="odd">
<td><p>Projection</p></td>
<td><p>Type</p></td>
</tr>
<tr class="even">
<td><p>Projection</p></td>
<td><p>ExtendedDataType</p></td>
</tr>
<tr class="odd">
<td><p>Projection</p></td>
<td><p>DisplayName</p></td>
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
<th><p>From Table: ExpressionTable</p></th>
<th><p>To Table: ExpressonElement</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>ParentElement</p></td>
</tr>
<tr class="even">
<td><p>ExpressionDefinition</p></td>
<td><p>Type</p></td>
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
<th><p>From Table: ExpressionTable</p></th>
<th><p>To Table: ExpressionPredicate</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>ExpressionFieldLHS</p></td>
</tr>
<tr class="even">
<td><p>ExpressionDefinition</p></td>
<td><p>ExpressionFieldRHS</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>RefRecIDValue</p></td>
</tr>
<tr class="even">
<td><p>ExpressionDefinition</p></td>
<td><p>RefTableIDValue</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>StringValue</p></td>
</tr>
<tr class="even">
<td><p>ExpressionDefinition</p></td>
<td><p>RealValue</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>LongValue</p></td>
</tr>
<tr class="even">
<td><p>ExpressionDefinition</p></td>
<td><p>EnumValue</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>AbsoluteDateValue</p></td>
</tr>
<tr class="even">
<td><p>ExpressionDefinition</p></td>
<td><p>StartDayType</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>OffsetDays</p></td>
</tr>
<tr class="even">
<td><p>ExpressionDefinition</p></td>
<td><p>DateOperatorType</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>ComparisonType</p></td>
</tr>
<tr class="even">
<td><p>ExpressionDefinition</p></td>
<td><p>DateType</p></td>
</tr>
<tr class="odd">
<td><p>ExpressionDefinition</p></td>
<td><p>Sequence</p></td>
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
<td><p>ExpressionProjectionDatasource</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>ExpressionProjectionField</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>ExpressionElement</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>ExpressionPredicate</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>ExpressionStagingTable</p></td>
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
<td><p>ExpressionTable</p></td>
<td><p>Projection</p></td>
</tr>
<tr class="even">
<td><p>ExpressionTable</p></td>
<td><p>ExpressionDefinition</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

