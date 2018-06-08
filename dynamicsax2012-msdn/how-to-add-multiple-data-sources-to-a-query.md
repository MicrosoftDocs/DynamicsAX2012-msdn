---
title: 'How to: Add Multiple Data Sources to a Query'
TOCTitle: 'How to: Add Multiple Data Sources to a Query'
ms:assetid: e3aa5cca-76b4-4932-add8-cad72211e1c6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa880078(v=AX.60)
ms:contentKeyID: 35253157
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Multiple Data Sources to a Query 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can add parent and child data sources to a query.


> [!NOTE]
> <P>If you add data sources at the same level, separate SQL statements are executed sequentially.</P>



To manage changes to AOT objects, a version control system is available. For more information, see [Version Control System](version-control-system.md).

Add multiple data sources to a query

1.  In the Application Object Tree (AOT), click **Queries**, locate the query you want to add data sources to, and then click the query node. For information about create queries, see [Accessing Data](accessing-data.md).

2.  Right-click **Data Dictionary**, and then click **Open New Window**.

3.  Drag a table, map, or view from the new window to the **Data Sources** node below the query node to add a parent data source.

4.  Click the parent data source, and then drag a table, map, or view from the new window to the **Data Sources** node below the parent data source to add a child data source.

5.  Specify how the parent and child data sources are joined by setting the **JoinMode** property on the child data source

6.  Create a relationship between the data sources. This information is provided later in the topic.

The following table describes the available values for the **JoinMode** property.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>InnerJoin</p></td>
<td><p>Combines records from two data sources whenever there are matching values in a common field.</p>
<p>For example, if you selected the records that show orders placed by each customer, the query would select only records for customers who placed orders.</p></td>
</tr>
<tr class="even">
<td><p>OuterJoin</p></td>
<td><p>Joins all the records in one data source even if there are no matching values in the joined field from the second data source.</p>
<p>This allows you to return records that do not have a corresponding match in the joined table. For example, data is required from all employees and their respective departments from the Employee table. As long as all employees are assigned to a department, an InnerJoin works. However, the president of the company does not have a department, and an inner join between the tables will not retrieve this data. The solution to this kind of problem is an outer join.</p></td>
</tr>
<tr class="odd">
<td><p>ExistsJoin</p></td>
<td><p>Combines records from one data source whenever there a value exists in a common field in another data source.</p>
<p>ExistsJoins are like InnerJoin, but MorphX uses only the embedded data source as a condition. Thus, the records in the embedded data source are not fetched by the query. The query will fetch the records in the primary data source only if a match is made with the embedded data source.</p></td>
</tr>
<tr class="even">
<td><p>NoExistsJoin</p></td>
<td><p>Selects records from one data source whenever a value in a common field in another data source does not exist. The opposite of ExistsJoin.</p></td>
</tr>
</tbody>
</table>


## Create a Relationship Between the Data Sources

  - Set the **Relations** property to **Yes** on the child data source.
    
    \-or-

  - Add a relation by doing the following:
    
    1.  Set the **Relations** property to **No** on the child data source.
    
    2.  Right-click the **Relations** node, and then click **New Relation**.
    
    3.  Select a field from the parent data source in the **Field** property.
    
    4.  Select a field from the child data source in the **RelatedField** property.
    
    5.  Save all modifications.

## See also

[Customizing the Query Form](customizing-the-query-form.md)

[Query Properties](https://msdn.microsoft.com/en-us/library/aa842737\(v=ax.60\))

[Using Expressions in Query Ranges](using-expressions-in-query-ranges.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

