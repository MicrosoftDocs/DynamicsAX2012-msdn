---
title: Tables, Views, and Maps
TOCTitle: Tables, Views, and Maps
ms:assetid: 9c62bde0-46a1-4b48-87b2-778a68627cd1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb395036(v=AX.60)
ms:contentKeyID: 35248218
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Tables, Views, and Maps 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Tables, views, and maps are elements that X++ SQL statements can reference to read and write business data. These elements are specified in the Application Object Tree (AOT) under **AOT** \> **Data Dictionary**. The following table describes these elements.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AOT element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tables</p></td>
<td><p>Tables store business data. Each table in the AOT has a corresponding table in the underlying Microsoft SQL Server database.</p>
<p>In Microsoft Dynamics AX, tables have advanced features beyond what tables might have in the underlying database. The advanced features include the following:</p>
<ul>
<li><p>Method members – A table can have methods, just as a class in X++ or C# can have methods.</p></li>
<li><p>Table inheritance – A table can extend, or be derived from another table. That same table can be the base table for several derived tables.</p></li>
<li><p>Valid time state – A table can be configured to track data relationships for specific date-time spans.</p></li>
</ul>
<p>Tables are specified at <strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Tables</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Views</p></td>
<td><p>A view is an X++ SQL select statement that is given a name that is reusable in other X++ SQL statements. The select statement of the view can reference one table, or it can join tables. Also, a view can reference other views, or a mix of views and tables. A view can also reference maps.</p>
<p>Developers are encouraged to consider using an AOT <a href="queries-in-the-aot-for-data-access.md">query</a> element as the source of data for their view.</p>
<p>Views are specified at <strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Views</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Maps</p></td>
<td><p>A map can unify the access to similar columns and methods that are present in multiple tables. You associate a map field with a field in one or more tables. This enables you to use the same field name to access fields with different names in different tables. Methods on maps enable you to create or modify methods that act on the table fields that the map references.</p>
<p>Maps are specified at <strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Maps</strong>.</p></td>
</tr>
</tbody>
</table>


A [query](queries-in-the-aot-for-data-access.md) can use tables, views, or maps for its data sources. Queries are specified at **AOT** \> **Queries**.

## In This Section

[Tables Overview](tables-overview.md)

[Temporary Tables and the TableType Property](temporary-tables-and-the-tabletype-property.md)

[Table Inheritance Overview](table-inheritance-overview.md)

[Valid Time State Tables and Date Effective Data](valid-time-state-tables-and-date-effective-data.md)

[Manipulation of Data in Tables](manipulation-of-data-in-tables.md)

[Record Level Security](record-level-security.md)

[How to: Define and Modify Table Methods](how-to-define-and-modify-table-methods.md)

[Map Overview](map-overview.md)

[View Overview](view-overview.md)

## See also

[Database for Microsoft Dynamics AX](database-for-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

