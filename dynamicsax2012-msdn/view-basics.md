---
title: View Basics
TOCTitle: View Basics
ms:assetid: 2adc61ef-0bc8-4460-b358-f8e28ee6b422
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314551(v=AX.60)
ms:contentKeyID: 35241783
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# View Basics [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX view is a virtual table that contains the data records and fields that are specified by a query. The following sections describe views and how they retrieve data.

## View Features

Like a table, a view uses fields and rows to represent data records. However, the data in a view is not stored as a database object but is dynamically created when the view is accessed. A view uses a query to retrieve data fields from one or more database tables.

In Microsoft Dynamics AX, you can use views where you use tables. For example, you can use a view in a form, a report, and in X++ code. The following table shows the benefits of using a view instead of a table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Benefit</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Focused data</p></td>
<td><p>A view enables you to retrieve and return only the data that is relevant for a particular user or scenario.</p></td>
</tr>
<tr class="even">
<td><p>Customized data</p></td>
<td><p>A view enables you use a complex query to create a highly-customized set of data. For example, a view often represents data as a single table that was retrieved from multiple joined tables and used many conditions.</p></td>
</tr>
<tr class="odd">
<td><p>Performance</p></td>
<td><p>A view can improve performance by returning only relevant fields to the user. In addition, a view definition is compiled which may provide better performance than calling an equivalently complex query.</p></td>
</tr>
</tbody>
</table>


When you create a view, the view definition is generated and stored in the database. When that view is accessed, the view dynamically retrieves the data that satisfies the view definition.


> [!NOTE]
> <P>Views are read-only. The data fields and tables that a view uses cannot be updated from that view.</P>



Views are synchronized like tables. When you synchronize a view, the view definition is saved to the database. Synchronization of an existing view causes the definition of that view to be dropped and re-created in the database.

To use X++ code to retrieve cross-company data from a view, you have to use the crossCompany keyword in the X++ select statement. For more information about how to retrieve cross-company data that uses a view, see [Cross-Company Queries for Views](cross-company-queries-for-views.md).

## View Elements

Views are located in the Application Object Tree (AOT) under the **Data Dictionary\\Views** node. A view contains four primary nodes:

  - Metadata

  - Fields

  - Field Groups

  - Methods

### ![Bb314551.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314551.collapse_all(en-us,AX.60).gif")Metadata

The **Metadata** node contains the query or data source that the view uses to retrieve data. A metadata query or data source is referred to as the view query. For more information about how to use a query or data source, see the View Query section later in this document.

### ![Bb314551.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314551.collapse_all(en-us,AX.60).gif")Fields

The Fields node specifies the data fields that the view returns. For example, the data source for the view named LedgerCustPaymProposal retrieves many fields from the table named LedgerJournalTrans. However, the view returns a small subset of the available fields. For more information about how to add fields to a view, see [How to: Create a View Based on a Query](how-to-create-a-view-based-on-a-query.md).

A view can return aggregate fields that use the functions SUM, MIN, MAX, AVG, and COUNT. Field aggregation is specified in the Aggregation property of the field. In Microsoft Dynamics AX, views support only field-level aggregation.


> [!NOTE]
> <P>To use the aggregation functions of COUNT, AVG, or SUM, the data field must be a data type of Integer or Real. If you try to use one of these aggregation functions on a field of any other data type, you will receive an error.</P>



### ![Bb314551.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314551.collapse_all(en-us,AX.60).gif")Field Groups

The Field Groups node contains the field groups for a view. A field group enables you to associates fields that logically belong together into named groups. Field groups in views work just like they do in tables. However, you can only add fields to a field group if those fields are returned by the view (each field must be located in the Fields node of that view). For more information about field groups, see [Best Practices for Field Groups](best-practices-for-field-groups.md), [Defining Field Groups](defining-field-groups.md), and [How to: Create a Field Group](how-to-create-a-field-group.md).

### ![Bb314551.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314551.collapse_all(en-us,AX.60).gif")Methods

The Methods node displays all the methods available from a view. Use this node to add a new method or override methods on the xRecord kernel class. Methods enable you to add code that customizes a view.

To add a new method:

1.  Expand the **Data Dictionary** \> **Views** node in the AOT.

2.  Navigate to the **Methods** node of the view.

3.  Right-click and select **New Method**.

4.  Enter your code in the Editor window and save your changes.

To override a method:

1.  Expand the **Data Dictionary** \> **Views** node in the AOT.

2.  Navigate to the **Methods** node of the view.

3.  Right-click and select **Override Method**.

4.  Select the method that you want to override.

5.  Enter your code in the Editor window and save your changes.

Methods that have been overridden display an icon with an arrow.

## View Query

The view **Metadata** node contains the query or data source that a view uses to retrieve data. There are currently two ways to define a view query:

  - Add an existing query to the **Metadata** node.

  - Add a single data table, map, or view to the **Data Sources** node of the **Metadata** node.

### ![Bb314551.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314551.collapse_all(en-us,AX.60).gif")Query

To define a view query, use a query from the AOT **Queries** node that retrieves the data for that view. A query object enables the flexibility to join tables, add filters, and group data to create a view that targets a specific user group or task. The following table shows the elements of a query that you use with a view.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Fields</strong></p></td>
<td><p>Use the list query fields to specify the data fields that the view returns.</p></td>
</tr>
<tr class="even">
<td><p><strong>Query</strong></p></td>
<td><p>To retrieve cross-company data, use a query with an AllowCrossCompany property that has the value of Yes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ranges</strong></p></td>
<td><p>Define a filter that specifies the types of records the view returns.</p></td>
</tr>
<tr class="even">
<td><p><strong>Relation</strong></p></td>
<td><p>Use joins to define relationships between source tables. In Microsoft Dynamics AX, views support only inner joins.</p></td>
</tr>
</tbody>
</table>


Once you create a query, that query can also be used as the data source for forms and reports related to the view. For more information about how to create a query, see [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md).

#### ![Bb314551.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314551.collapse_all(en-us,AX.60).gif")Views and Queries

To use a query with a view, drag the query object from the AOT queries node to the **Metadata** node of that view. After you add the query to the **Metadata** node, use the fields from that query to add one or more fields to the view. The view definition is not created until you add a field to the view. For more information about how to add a query and fields to a view, see [How to: Create a View Based on a Query](how-to-create-a-view-based-on-a-query.md).


> [!NOTE]
> <P>The view <STRONG>Metadata</STRONG> node can contain only one query. If you drag a second query onto the <STRONG>Metadata</STRONG> node of a view, the second query will replace the existing query.</P>



Do not add a query with a QueryType of Join that has a disabled data source to the **Metadata** node of a view. If any data source element in that query is marked as disabled or the data source element is disabled by a configuration or license key, the view will not return any data. You can use a query with a QueryType of Union that has a disabled data source as long as the disabled data source is not the first data source in the query.

If a change is made to the query that removes a data field that the view returns, the view query is not changed. The view uses the underlying table data source to retrieve the field. While the view continues to return the expected data, the view definition no longer aligns with the structure of the specified query. This prevents a change to the query from disabling any views that use that query as a data source.

#### ![Bb314551.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314551.collapse_all(en-us,AX.60).gif")Cross-company Views

To create a view that returns cross-company data, use a query with an AllowCrossCompany property value of Yes. For more information about cross-company queries, see [Cross-Company Data Access](cross-company-data-access.md).

### ![Bb314551.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314551.collapse_all(en-us,AX.60).gif")Data Sources

The alternative to using a query object for a view query is to add a single table, map, or view to the **Data Sources** node of the **Metadata** node of the view. To add a data source, use the AOT to drag a table, map, or view onto the **Data Sources** node of that view. Use the data fields from that table, map, or view to add one or more fields to the view. The view definition is not created until you add a field to the view.


> [!NOTE]
> <P>You cannot add a table, map, or view to a view if you previously added a query to the metadata node.</P>



Do not use multiple tables, maps, or views to define the data source of a view. If you have to use multiple tables in a view, create a query that retrieves the data and drag that query onto the **Metadata** node of the view.


> [!NOTE]
> <P>The ability to use multiple tables, maps, or views as a data source is expected to be removed in a future version of Microsoft Dynamics AX.</P>



The data sources node enables you to define the hierarchy of data sources that the view uses to retrieve data. To build a data source hierarchy, you can nest data sources. Nesting a data source refers to adding a child data source to an existing parent data source.

To nest the data sources for a view, you can use the **Data Sources** element of the table, map, or view to specify the child data source. For example, if you add a table to the metadata data sources node, you can use the **Data Sources** element of that table to create a join to another table.


> [!NOTE]
> <P>A view limits data source nesting so that each level of the hierarchy contains a single child data source. For example, after you join a child table to the parent table you cannot add a second table to the data sources node of the parent table.</P>



Once you add a query, table, map, or view to the data sources node, you cannot use the AOT to drag a new query, table, map, or view to the data sources node of the metadata node of the view. If you do, the operation is ignored and the existing table, map, or view remains the data source. To change a data source, you must first delete the existing data source elements.

The following table lists the elements of a data source and describes how they are used in a view.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Fields</p></td>
<td><p>Lists all the data fields that the query, table, map, or view returns. To specify the fields that the view returns, you add fields from this list to the <strong>Fields</strong> node of the view. When you add a data source to a view, the value of the Dynamic property of the <strong>Fields</strong> element is made read-only so that you cannot add or remove fields at the data source level.</p></td>
</tr>
<tr class="even">
<td><p>Data Sources</p></td>
<td><p>Identifies the child data source of the current data source. In a view, data sources can be nested. To create a nested data source, you can add a child data source to an existing parent data source. The child data source has its own set of data source elements. The child data source includes the <strong>Relations</strong> element.</p></td>
</tr>
<tr class="odd">
<td><p>Group By</p></td>
<td><p>Do not specify a field in the <strong>Group By</strong> element. A view does not use the field information in the <strong>Group By</strong> element.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
If you want to group the records in a view, replace the view data source with a query that has the specified group by information.
</div>
</div></td>
</tr>
<tr class="even">
<td><p>Order By</p></td>
<td><p>Do not specify a field in the <strong>Order By</strong> element. A view cannot use the field information in the <strong>Order By</strong> element.</p></td>
</tr>
<tr class="odd">
<td><p>Ranges</p></td>
<td><p>Lists the range objects that the data source uses to filter the records that the data source returns. A range object includes two properties you can use to create filter criteria. The Field property specifies the data field that participates in the range expression. The Value property specifies the expression that defines the filter criteria. The data source returns the data records that meet the specified criteria.</p>
<p>A view data source range performs the same task as a query range. For more information about query ranges, see <a href="query-elements-in-the-aot.md">Query Elements in the AOT</a>.</p></td>
</tr>
<tr class="even">
<td><p>Relations</p></td>
<td><p>Defines how a parent data source is related to a child data source. The relation object enables the view to combine a data record from the parent data source with a data record from the child data source.</p>
<p>For example, the view named InventCostTransView has a data source named InventDim. The InventDim data source has a child data source named InventCostTrans. To define how individual records are related, a relation object is added to the InventCostTrans data source. The Field and Related Field properties identify the data source fields that the relation uses to match parent data source records to child data source records. In this example, a parent record is matched to a child record when the value in the <strong>inventDimId</strong> field of the parent data source is equal to the value in the <strong>FinancialInventDimId</strong> of the child data source. Once the relationship is defined, the view can use columns from both tables.</p>
<p>Each child data source has an underlying table, map, or view that has a Relations property that is set to No. If this property is set to Yes, Microsoft Dynamics AX can automatically add a relation from the child data source to the parent data source. For more information about how to use relation objects, see <a href="query-elements-in-the-aot.md">Query Elements in the AOT</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[How to: Create a View Based on a Query](how-to-create-a-view-based-on-a-query.md)

[View Properties](https://msdn.microsoft.com/en-us/library/aa869223\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

