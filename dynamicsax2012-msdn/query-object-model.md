---
title: Query Object Model
TOCTitle: Query Object Model
ms:assetid: 3e83a1b2-88cc-46d8-a3ca-ff19da59882a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa625948(v=AX.60)
ms:contentKeyID: 35242943
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Query Object Model 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The query object model contains classes to define and run a query. These objects are used to define the query data source, the fields returned, record ranges and relations to child data sources. The following illustration shows the object model.

![The Structure of a Query](images/Aa625948.QueryStructure(en-us,AX.60).gif "The Structure of a Query")

The query components shown in the previous figure are system classes. The query classes are more visible when you [create a dynamic query in code](how-to-create-queries-by-using-x.md), but they are also used behind the scenes when you [create a static query in the AOT](how-to-create-queries-by-using-the-aot.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>System class</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg923354(v=ax.60)">QueryRun</a></p></td>
<td><p>Executes the query and fetches the data.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg913387(v=ax.60)">Query</a></p></td>
<td><p>The top level of the query definition. This class holds some properties itself and has one or more related data sources.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg913612(v=ax.60)">QueryBuildDataSource</a></p></td>
<td><p>Defines access to a single data source in the query. If more than one data source exists at the same level in a query, they result in separate SQL statements that are executed sequentially. If one data source exists as a child of another data source, a join is created between the two data sources.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg913662(v=ax.60)">QueryBuildFieldList</a></p></td>
<td><p>Defines which fields are returned from the database. The default is that the field list is dynamic, which returns all fields from the data source table, map, or view. Each data source has only one QueryBuildFieldList object, which contains information on all selected fields. It's possible to specify aggregate functions like SUM, COUNT, and AVG on the field list object.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg913682(v=ax.60)">QueryBuildRange</a></p></td>
<td><p>Defines a subset of records returned based on a single field. A range is translated into a WHERE clause in the query SQL statement. If more than one field is used to limit the query (WHERE clause), the data source will contain more than one range.</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg913654(v=ax.60)">QueryBuildDynalink</a></p></td>
<td><p>Contains information regarding a relation (limitation) to an external record. When the query is run, this information is converted to additional entries in the WHERE clause of the query SQL statement. Can only exist on the parent data source of a query. The function is used by forms, when two data sources are synchronized. Then the child data source will contain a dynalink or dynalinks to the parent data source. The function is used even if the two data sources are placed in two different forms but are still synchronized.</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg913668(v=ax.60)">QueryBuildLink</a></p></td>
<td><p>Specifies the relation between the two data sources in the join. Can only exist on a child data source.</p></td>
</tr>
</tbody>
</table>


## See also

[How to: Create Queries by Using X++](how-to-create-queries-by-using-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

