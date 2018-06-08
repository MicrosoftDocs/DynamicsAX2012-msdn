---
title: Data Sources for Forms
TOCTitle: Data Sources for Forms
ms:assetid: 185149d7-d5ce-4923-a751-f565f0827784
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844014(v=AX.60)
ms:contentKeyID: 35241366
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Data Sources for Forms 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A form data source supplies the data that appears on a form. To display data, you assign a data field from the form data source to a property of a control that appears on the form.

## Types of Data Sources

You can use the following AOT elements as a data source for a form.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Source</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Query</p></td>
<td><p>A query is a business object in the <strong>Queries</strong> node of the AOT. A query uses tables, maps, or views to retrieve a set of data fields. To use a query as a form data source, you use the <strong>Query</strong> property of the <strong>Data Sources</strong> node to specify the query for the form.</p>
<p>You might find that a query has set the <strong>Dynamic</strong> property of the <strong>Fields</strong> node to <strong>No</strong>. You set <strong>Dynamic</strong> to <strong>No</strong> when you want to specify the list of fields that appear in the query. When you add that query to the <strong>Data Sources</strong> of a form, the list of fields in the table node include all the fields for the table. For more information about queries, see <a href="query-elements-in-the-aot.md">Query Elements in the AOT</a>.</p></td>
</tr>
<tr class="even">
<td><p>Table</p></td>
<td><p>A table is a business object in the <strong>Data Dictionary</strong> node of the AOT. A table is an object that contains data records for the system. In addition, a table can define a table relation that enables you to look up data from a referenced table. For more information about tables, see <a href="tables-overview.md">Tables Overview</a>.</p>
<p>To add a table to a form, you drag the table from <strong>Data Dictionary</strong> &gt; <strong>Tables</strong> onto the <strong>Data Sources</strong> node of the form. You can also right-click <strong>Data Sources</strong>, click <strong>New DataSource</strong>, and then use the <strong>Table</strong> property of the new data source to specify the table.</p>
<p>Do not add a table to the form data source where the <strong>Visible</strong> property of the table is <strong>No</strong>. The property specifies whether controls bound to that table will be visible on the form. If you try to open a form that includes a table specified as not visible, you will see an Infolog error message. To try to prevent the error message, you can set the <strong>AllowCheck</strong> property of the table in the form data source to <strong>No</strong>. The form will no longer check permissions for the specified table.</p></td>
</tr>
<tr class="odd">
<td><p>View</p></td>
<td><p>A view is a business object in the <strong>Data Dictionary</strong> node of the AOT. A view is a stored query that retrieves a specified collection of data records and fields. The data in a view is retrieved when the view is accessed. For more information about views, see <a href="view-basics.md">View Basics</a>.</p>
<p>To add a view to a form, you drag the view from <strong>Data Dictionary</strong> &gt; <strong>Views</strong> onto the <strong>Data Sources</strong> node of the form.</p></td>
</tr>
</tbody>
</table>


You might have X++ code in a form or control that attempts to access field that is not included in the select list of the data source. If the form or a control attempts to access a field that was not retrieved, an X++ exception is thrown. In addition, information about the error is added to the Infolog.

To see whether the field is available, use the isFieldDataRetrieved method. You can also add the specified field to the select list of the data source or remove the code that attempts to access the field.

## Using Base and Derived Tables with a Form Data Source

The Microsoft Dynamics AX application object server enables you to specify inheritance between database tables. A table inheritance hierarchy is a collection of tables where each table derives from another table in the hierarchy. The table at the root of the hierarchy is known as the base table. The other tables in the hierarchy extend or derive from the base table. Each derived table adds fields and methods that extend the type described by the base table. For more information about table inheritance, see [Table Inheritance Overview](table-inheritance-overview.md).

You can use the base or derived table in a table inheritance hierarchy as a form data source. A form that has a base table for a form data source will include one or more derived data sources. The derived data sources enable you to view, create, or update related types of records from the form. For more information about table inheritance and derived data sources, see [Derived Data Sources for Forms](derived-data-sources-for-forms.md).

## Using Lookup Forms with a Form Data Source

A form data source can include a table that has a table relation. The table relation links a record in the form data source table to a record in a separate table. The table relation uses a foreign key to link to the related record. A foreign key is a column or combination of columns whose values identify the primary key of a record in a table. The table whose primary key populates the foreign key field is known as the referenced table.

The table relation enables you to add a lookup form to a field. The lookup form enables you to view and select a record from the referenced table. When you select a record in the lookup form, the primary key of that record populates the foreign key field of the table. For information about lookup forms, see [Lookup Forms Overview](lookup-forms-overview.md).

The following table describes the types of keys in a table relation that enable you to use a lookup form.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Primary key type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Natural key</p></td>
<td><p>You use the values in one or more columns to uniquely identify a record. The column or columns contain meaningful data values. For example, you could use CompanyName and PostalCode as a natural key for the records in a table.</p></td>
</tr>
<tr class="even">
<td><p>Surrogate key</p></td>
<td><p>You use the value in a single column to uniquely identify a record. The value in the column is usually a counter or a very large integer where duplication is very unlikely. In addition, the key value is only used to identify the record and should not appear on a form.</p></td>
</tr>
</tbody>
</table>


## Using Joins with Form Data Source Tables

You can add more than one table to a form data source. If one table includes a foreign key that is the primary key of the second table, you can establish a join between the two tables. You join tables in a form data source to obtain the following advantages:

  - You want to use them like a single data source. For example, you join two tables and display fields from each table on the form using a grid. If you modify or add a record in the grid, neither table is updated until the grid row is exited.

  - You want to reflect a parent and child relation between the tables. Typically, the data from the joined tables is visually separated. For example, order records are shown as the parent data source in one grid and order lines appear in a second grid as the child data source.

  - You want to improve performance. A select, insert, or update operation occurs across all the tables in the join relationship.
    

    > [!TIP]
    > <P>You can programmatically display data from other data sources by using methods that have display or edit method modifiers. However, a join performs better than using these types of methods.</P>



  - You want to synchronize navigation between tables. For example, every time that you select a new record, both data sources are updated at the same time.

  - You want to specify how form data source methods run for the tables in the form data source. Form data source methods such as active, next, and executeQuery are directed to the parent table of the join. However, the init method is run for all tables in the form data source.

### ![Gg844014.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844014.collapse_all(en-us,AX.60).gif")Setting the JoinSource Property

To establish a join between two form data sources, you populate the **JoinSource** property of one data source. You use the property to identify a data source that has a foreign key table relation with the current data source. For information about how to use the **JoinSource** property, see [How to: Join Data Sources for a Form](how-to-join-data-sources-for-a-form.md).

### ![Gg844014.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844014.collapse_all(en-us,AX.60).gif")Setting the LinkType Property

You use the **LinkType** property to specify the type of join you want for the form. You use the join to combine data sources so that the fields appear to be from a single data source. You can set the **LinkType** property to **InnerJoin**, **OuterJoin**, **ExistJoin**, or **NotExistJoin**. To join tables that have a parent and child relationship, you set the **LinkType** property to **Passive**, **Delayed**, or **Active**. The following table describes the values that you can use to populate the LinkType property.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>LinkType</p></th>
<th><p>Join type</p></th>
<th><p>How the join is performed</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Active</strong></p></td>
<td><p>Parent and child</p></td>
<td><p>The data source is updated immediately when a new record in the parent data source is selected. Continuous updates consume lots of resources.</p></td>
</tr>
<tr class="even">
<td><p><strong>Delayed</strong></p></td>
<td><p>Parent and child</p></td>
<td><p>A pause is inserted before linked child data sources are updated. This enables faster navigation in the parent data source because the records from child data sources are not updated immediately. For example, you can scroll a list of orders where you do not want to review the lines associated with the order until you stop scrolling.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExistJoin</strong></p></td>
<td><p>Combined data source</p></td>
<td><p>The data source retrieves a record from the main table for each matching record in the joined table.</p>
<p>The differences between <strong>InnerJoin</strong> and <strong>ExistJoin</strong> are as follows:</p>
<ul>
<li><p>When the join type is <strong>ExistJoin</strong>, the search ends after the first match has been found.</p></li>
<li><p>When the join type is <strong>InnerJoin</strong>, all matching records are searched for.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>InnerJoin</strong></p></td>
<td><p>Combined data source</p></td>
<td><p>Retrieves a record from the main table that matches records in the joined table and vice versa.</p>
<p>There is one record for each match. Records without related records in the other data source are eliminated from the result.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NotExistJoin</strong></p></td>
<td><p>Combined data source</p></td>
<td><p>Select records from the main table that do not have a match in the joined table.</p></td>
</tr>
<tr class="even">
<td><p><strong>OuterJoin</strong></p></td>
<td><p>Combined data source</p></td>
<td><p>The data source retrieves records from the main table. The records are retrieved whether they have matching records in the joined table.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Passive</strong></p></td>
<td><p>Parent and child</p></td>
<td><p>Linked child data sources are not updated automatically. Updates of the child data source must be programmed on the active method of the master data source.</p></td>
</tr>
</tbody>
</table>


## See also

[How to: Join Parent/Child Data Sources for a Form](how-to-join-parent-child-data-sources-for-a-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

