---
title: Best Practices for Views
TOCTitle: Views
ms:assetid: 81e5c24f-123a-4957-aa58-4cf15dbc69e3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa643254(v=AX.60)
ms:contentKeyID: 35246145
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Views [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic contains information about the best practices for setting view properties and view field properties.

## View Properties

The properties that are available for views are a subset of the [properties available for tables](best-practices-for-table-properties.md). Views are read-only, and so some of the properties are set by default and cannot be changed. Best practices are listed for some of the properties that can be edited:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Cannot have same name as a class, table, map, enum, or data type.</p>
<p>Prefix with the module name, for example: Cust, Ledger, Proj.</p>
<p>Infix with a logical description of contents, for example ProjCommittedCostCategoryView, where &quot;ComittedCostCategory&quot; is the infix.</p>
<p>You can use 'View' as a postfix.</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Mandatory property.</p>
<p>The text value of the Label must be unique across all tables, views, and maps, in all languages.</p></td>
</tr>
<tr class="odd">
<td><p>TitleField1, TitleField2</p></td>
<td><p>TitleField1 is the title that is used on forms that use the view as main datasource.</p>
<p>TitleField2 is the secondary title and is used on forms that use the view as main datasource.</p></td>
</tr>
<tr class="even">
<td><p>AnalysisVisibility, AnalysisSelection, TypicalRowCount, IsLookup, SingularLabel</p></td>
<td><p>These properties are inherited from tables, where they are used as part of the end-user reporting system. End-user reporting is not implemented for views, and so any best practice errors about these properties should be ignored for views.</p></td>
</tr>
</tbody>
</table>


## View Field Properties

Many of the properties that are available for view fields are also available as properties on table fields. The best practice advice is the same as for table field properties.

## See also

[Best Practices for Table Field Properties](best-practices-for-table-field-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

