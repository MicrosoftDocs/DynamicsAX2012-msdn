---
title: Query Elements in the AOT
TOCTitle: Query Elements in the AOT
ms:assetid: 014829c0-3191-428d-b65a-af1a5ec58ced
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb278121(v=AX.60)
ms:contentKeyID: 35240082
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- sql
---

# Query Elements in the AOT [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Static queries are pre-defined queries that can be accessed from the Application Object Tree (AOT). In Microsoft Dynamics AX, static queries are located in the **Queries** node and contain the following primary subnodes:

  - **Methods**

  - **Data Sources**

  - **Dependent Objects**

  - **Composite Query**

Each Data Sources node has the following subnodes:

  - **Fields**

  - **Ranges**

  - **Data Sources**

  - **Group By**

  - **Order By**

  - **Relations** (only present in a child data source)

## Methods

The **Methods** node displays all the methods available from a query. In this node you can add a new method to a query. You can also override methods on the QueryRun system class and add your own code to class methods inherited from the [QueryRun](https://msdn.microsoft.com/en-us/library/gg923354\(v=ax.60\)) class. Only new methods and overridden methods appear in the **Queries** node except for the classDeclaration method which is always present.

To add a new method:

1.  Navigate to the **Queries** node in the AOT, right-click the node and, then select **New Method**.

2.  Enter your code in the **Editor** window and save your changes.

To override a method:

1.  Navigate to the **Queries** node in the AOT, right-click the node, and then select **Override Method**.

2.  Select the method that you want to override.

3.  Enter your code in the **Editor** window and save your changes.

Methods that have been overridden display an icon with an arrow.

## Data Sources

The **Data Sources** node contains a hierarchy of data sources from which the query gets its data. A query data source can be a table, map, or view.

Data sources can be embedded inside each other (nested). A nested data source is referred to as a child data source of the parent data source. A child data source has all the standard data source elements, and it also contains a relations element. The relation is used to define how the parent data source is related to the child data source. Whenever a record in the parent data source is selected, the child records are selected based on the relation that is defined and any record ranges that are specified.

If there is more than one data source at the same level, the query accesses the data sources sequentially and fetches the records from each of them.

### ![Bb278121.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278121.collapse_all(en-us,AX.60).gif")Fields

The **Fields** node contains the data elements returned by the table, map, or view. If you set the **Fields** node **Dynamic** property to **Yes**, all the fields in the data source are returned. If you set the **Dynamic** property to **No**, you can right-click a field and select **Delete** to remove it from the data source.

The **Fields** node enables you to add an aggregate field based on a field in the source table, map, or view. The aggregate functions that are available are **AVG**, **SUM**, **COUNT**, **MIN**, or **MAX**.

### ![Bb278121.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278121.collapse_all(en-us,AX.60).gif")Ranges

The **Ranges** node contains ranges that limit the number of records returned by the query to only those that match the range expression. The **Field** property of the **Range** defines the field that participates in the range expression. The **Value** property of the **Range** contains the expression that defines the conditions to be met by the records returned by the data source.

For example, you can limit the number of records that are return by a query against the **CustTable** table. You can limit the returned rows to those that contain specific **AccountNum** values. The following shows the defined range expression.

``` sql
..5000, 5012..5014, 5500, !6500, 6000..
```

This range expression retrieves:

  - Records with **AccountNum** values less than or equal to 5000.

  - Records with **AccountNum** values from 5012 to 5014 inclusive.

  - Records with the **AccountNum** equal to 5500.

  - Records with **AccountNum** values above 6000, except for any records with the **AccountNum** equal to 6500.

Range expressions on different fields are combined by using the AND expression. Range expressions on the same field are combined by using the OR expression. The following table lists the operators and symbols that can be used in range expressions.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Symbol</p></th>
<th><p>Meaning</p></th>
<th><p>Example</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>=</p></td>
<td><p>Equal to</p></td>
<td><p>=Smith</p></td>
<td><p>Finds Smith.</p></td>
</tr>
<tr class="even">
<td><p>!</p></td>
<td><p>Not equal to</p></td>
<td><p>!Smith</p></td>
<td><p>Finds all values except Smith.</p></td>
</tr>
<tr class="odd">
<td><p>..</p></td>
<td><p>Between two values</p></td>
<td><p>A..C</p></td>
<td><p>Finds all records from A to C including records with A and C.</p></td>
</tr>
<tr class="even">
<td><p>&gt;</p></td>
<td><p>Greater than</p></td>
<td><p>&gt;1000</p></td>
<td><p>Finds all values greater than 1000.</p></td>
</tr>
<tr class="odd">
<td><p>&lt;</p></td>
<td><p>Less than</p></td>
<td><p>&lt;1000</p></td>
<td><p>Finds all values less than 1000 including negative values.</p></td>
</tr>
<tr class="even">
<td><p>*</p></td>
<td><p>Match values that contain the characters before or after the asterisk</p></td>
<td><p>S*</p>
<p>or</p>
<p>*east*</p></td>
<td><p>Finds all values that begin with the letter S.</p>
<p>Finds all values that include the word east.</p></td>
</tr>
<tr class="odd">
<td><p>?</p></td>
<td><p>Matches a single unknown character</p></td>
<td><p>Sm?th</p></td>
<td><p>Finds all values that include only the letters s, m, t, and h in the order shown and any character in the ? placeholder</p></td>
</tr>
<tr class="even">
<td><p>,</p></td>
<td><p>Separates expression components</p></td>
<td><p>A..D, !C</p></td>
<td><p>Finds A, B, and D.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>Complex range expressions can affect performance. The more filter expressions Microsoft Dynamics AX must apply to the data the longer the query will take to run.</P>



Ranges can also be defined in dynamic queries using X++. For more information, see [expressions in query ranges](using-expressions-in-query-ranges.md).

### ![Bb278121.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278121.collapse_all(en-us,AX.60).gif")Group By

You use the **Group By** node to restrict the field combination listed to only the unique value combinations in their data. The other fields in the query must all be processed by aggregate functions.

For example, in your query of the table **CustTrans** you could list the columns **AccountNum** and **TransType** under **Group By**. This would ensure that the retrieved data would not include the value combination of 4004 and Purch more than one time. The column **AmountCur** could be a sum of every **AmountCur** from every database row that had the value pair of 4004 and Purch.

### ![Bb278121.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278121.collapse_all(en-us,AX.60).gif")Order By

The **Order By** node contains the sort order for the data source. Sort order is defined on a field or index in the table, map, or view on which the data source is based. Therefore, you can sort the query results on a field that is in the table whether that field is returned by the query (listed in the **Fields** node). A query can be sorted on multiple fields in ascending or descending order.

If the query data source is a table, an index can be specified in the **Sorting** node. When an index is specified as the sort order for a query, the query does not create a new index but rather uses the sort order in an existing table index.


> [!NOTE]
> <P>Sorting can affect performance. For example if a sort is defined on a long string field, the query returns a large data set. To improve performance, sort on numeric or indexed fields. If you must sort on a long string field such as <STRONG>CustName</STRONG>, limit the number of records returned by the query by using a range.</P>



### ![Bb278121.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278121.collapse_all(en-us,AX.60).gif")Relations

The **Relations** node contains the group of relation properties that define a join between the child data source and another data source in the query. To create joins between data sources, add one or more groups of relation properties to the **Relations** node. The **Relations** node is only found in a child data source. For more information about how to add a relation, see [How to: Add Multiple Data Sources to a Query](how-to-add-multiple-data-sources-to-a-query.md).

The **JoinMode** property on the child data source indicates the type of join that exists between a parent data source and a child data source. The options for the **JoinMode** property are **InnerJoin**, **OuterJoin**, **ExistsJoin**, or **NoExistsJoin**. For more information about how to set the **JoinMode** property, see [How to: Add Multiple Data Sources to a Query](how-to-add-multiple-data-sources-to-a-query.md).

To specify the data sources and data fields to use in the join, use the AOT to right-click the **Relations** node of a child data source, and then click **New Relation**. There are two methods for defining a relation between data sources:

  - Use the relation that is automatically created. By default, each child data source's underlying table, map, or view has a **Relations** property that is set to **Yes**. When this property is set to **Yes**, Microsoft Dynamics AX automatically adds a relation from the child data source to the parent data source. In this case, if there is an existing table relation between the two tables, the new relation is based on the existing table relation. If there is no existing table relation, the new relation is created based on an existing relation on an extended data type.
    
    For example, the **SalesQuotationUpdate** query has a data source of the **SalesQuotationTable**. This data source has a child data source of table **SalesQuotationLine**. When a relation is created automatically for these two tables, it occurs through an existing table relation on the **SalesQuotationLine** table. The **SalesQuotationLine** table has a child data source of the **InventDim** table. When a relation is created automatically for these two tables, it is based on the existing relation on the extended data type **InventDimId**.

  - Use the AOT to specify the value of each relation property. Set property values that identify the fields and data sources to use to create the join. When the query executes, the values of the relation properties together with the **JoinMode** property value determine how the field data from one data source is used to retrieve data from the other data source. To define a join, set the value of the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>CurrentDataSource</strong></p></td>
    <td><p>Specifies the name of the current child data source. You cannot change the value of this property.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Field</strong></p></td>
    <td><p>Select the field from the join data source to use in the join. When the query executes, the join uses the data value in this field to identify child data source records that have the same data value in the field specified by the <strong>RelatedField</strong> property.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>JoinDataSource</strong></p></td>
    <td><p>Select the data source that you want to join with the current data source. The drop-down list displays the available data sources in the query. When you click a data source, you specify the parent data source of the join.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>RelatedField</strong></p></td>
    <td><p>Select the field from the current data source to use in the join. When the query executes, the join uses the data values from this field and the <strong>Field</strong> property to match child data source records to parent data source records.</p></td>
    </tr>
    </tbody>
    </table>


## Dependent Objects

The **Dependent Objects** node contains a node for every AOT object that references the query, such as forms and reports. This shows you which objects are affected when you modify the query.

## Composite Query

A query can be based on another query, as a mechanism for efficient reuse of the original query. You drop the original query onto this node, instead of onto the **Data Sources** node.

For more information, see [Query Reuse by Composite Queries](query-reuse-by-composite-queries.md).

## See also

[How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md)

[Using Expressions in Query Ranges](using-expressions-in-query-ranges.md)

[Query System Classes](query-object-model.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

