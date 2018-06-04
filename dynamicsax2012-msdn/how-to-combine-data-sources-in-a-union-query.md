---
title: 'How to: Combine Data Sources in a Union Query'
TOCTitle: 'How to: Combine Data Sources in a Union Query'
ms:assetid: 950be09c-9acb-4722-affc-7827a124c8b3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc605991(v=AX.60)
ms:contentKeyID: 35247612
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Combine Data Sources in a Union Query 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX query can retrieve data that represents the combination of two or more data sources. To combine data sources, use the AOT to create a union query. When you create a union query, determine how the following constraints affect your query:

  - All the data sources in a union query must have the same structure. Each data source must have the same number of columns, and the corresponding columns of each data source must be the same data type. A union query does not support implicit or explicit conversions between data types.

  - A union query uses the field names from the first data source as the column names for that query. You cannot customize the column names.

  - A union query uses the sort order information that is contained in the Order By element of the first data source. Any Order By information in the remaining data sources is ignored.

  - You cannot use a union query to update records. When you create the query in the AOT, the value of the Update property of each data source is automatically set to No and cannot be changed.

  - Union queries can only be created in the AOT. You cannot use X++ to create a union query.

The following procedure explains how to create a union query.

### To create a union query

1.  In the AOT, right-click **Queries**, and then click **New Query**. A query node is added in the AOT.

2.  Right-click the new query node, and then click **Properties**. The properties window opens and displays the query properties. Set the value of the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the query.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>QueryType</strong></p></td>
    <td><p><strong>Union</strong></p></td>
    </tr>
    </tbody>
    </table>


3.  Expand the new query node, right-click **Data Sources**, and then click **New Data Source**. A new data source is added to the **Data Sources** node.

4.  Click the data source to display its properties in the **Properties** window. Set the value of the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the data source.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Table</strong></p></td>
    <td><p>Select the table that you want to use. For example, click CustTable.</p></td>
    </tr>
    </tbody>
    </table>


5.  Expand the new data source, and then expand the **Fields** node. Specify the fields to use with the union. For example, use CustTable as the data source. In the **Fields** for that data source, keep **AccountNum**, **Name**, **City**, and **SegmentId** and remove all other fields.

6.  Right-click the **Data Sources** node, and then click **New Data Source**. A new data source is added to the **Data Sources** node.

7.  Click the data source to display its properties in the **Properties** window. Set the value of the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies the data source.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Table</strong></p></td>
    <td><p>Select the table that you want to use. For example, click VendTable.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>UnionType</strong></p></td>
    <td><p>Specify the type of union. Click <strong>Union</strong> to eliminate duplicate records. Click <strong>UnionAll</strong> to include duplicate records.</p></td>
    </tr>
    </tbody>
    </table>


8.  Expand the new data source, and then expand the **Fields** node. Specify the fields to use with the union. The number, order, and data type of each column must match the fields selected in the first data source. To continue the previous example, add VendTable, as a data source. To match the **CustTable** data source, keep the **AccountNum**, **Name**, **City**, and **SegmentId** fields and remove all other fields.

9.  To include additional data sources, repeat the previous two steps for each data source.

10. In the AOT, right-click the query, and then click **Save**.

A union query returns the specified data for each record in each data source. To view the results from a union query, add the query as the data source for a form or report that displays the query results. For example, create a list page with a data source that uses a union query that combines CustTable and VendTable. The union query retrieves the **AccountNum**, **Name**, **City**, and **SegmentId** for each record. When you view the list page, it displays the specified data fields for each customer and vendor of the company.

## See also

[How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md)

[Query Properties](https://msdn.microsoft.com/en-us/library/aa842737\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

