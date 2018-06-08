---
title: 'How to: Add a Data Source to a Primary List Page'
TOCTitle: 'How to: Add a Data Source to a Primary List Page'
ms:assetid: 3a3cf68e-b824-4d4e-a462-3b769fb216e4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc596921(v=AX.60)
ms:contentKeyID: 35242878
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Data Source to a Primary List Page 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A primary list page displays a collection of records from the Microsoft Dynamics AX database. Typically, you use a query to specify the records that appear in the list page.


> [!NOTE]
> <P>While a query is the best way to add a data source to a list page, you can use a table as a data source. For information about how to use a table as a form data source, see <A href="walkthrough-creating-a-form-by-using-the-aot.md">Walkthrough: Creating a Form by Using the AOT</A>. For information about how to use more than one table as a data source, see <A href="how-to-join-data-sources-for-a-form.md">How to: Join Data Sources for a Form</A>.</P>



The following procedures describe how to use query as the data source of a list page.

### To find or create the query for the list page

1.  In the AOT, expand the **Queries** node, and then search the list of queries.
    

    > [!TIP]
    > <P>Typically, the query you use for a list page data source includes <STRONG>ListPage</STRONG> in the query name. For example, the query for the customer list page is named <STRONG>CustTableListPage</STRONG>.</P>



2.  If you find a query that you want to use, verify that the query returns the records and data fields that you want to appear in the list page.

3.  If you cannot find a query that provides the information that you need for the list page, you will have to create a new query. To create a query, see [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md). When you specify a name for the query, make sure that the name ends with **ListPage**.

4.  Note the name of the query. You will use this query as the data source for the list page.

### To add a data source to a list page

1.  Open a second AOT window, expand the **Forms** node, and search for the list page that needs a data source. Expand the form node for the specified list page.
    

    > [!NOTE]
    > <P>If you have to create a new form for the list page, see <A href="how-to-create-a-list-page-form.md">How to: Create a List Page Form</A>.</P>



2.  To add a data source, click the **Data Sources** node. In the **Properties** window, expand **Query**, and then click the name of the query that you identified in the previous procedure.

3.  Expand the **Data Sources** node for the list page. The node includes the query that you added and the data sources associated with that query.

4.  Right-click the first data source, and then click **Properties**. Verify that the following properties have the specified values.
    
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
    <td><p><strong>AllowCreate</strong></p></td>
    <td><p><strong>No</strong>. Do not use the list page to create a new record.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>AllowEdit</strong></p></td>
    <td><p><strong>No</strong>. Do not use the list page to update an existing record.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>StartPosition</strong></p></td>
    <td><p><strong>First</strong></p></td>
    </tr>
    </tbody>
    </table>


5.  If more than one data source is associated with the query, repeat the previous step for each data source that was added for the list page form.

6.  Save the form by right-clicking the form name, and then clicking **Save**. Close the AOT window that is displaying **Queries**.

After you add the data source, you can add fields to the grid control to the list page form. For information about how to add fields to a list page grid, see [How to: Add Fields to the List Page Grid](how-to-add-fields-to-the-list-page-grid.md).

You should also specify the form that opens when you double-click a record in that grid. For more information, see [How to: Specify the Default Action for the List Page Grid](how-to-specify-the-default-action-for-the-list-page-grid.md)

## See also

[List Page Forms](list-page-forms.md)

[Queries in the AOT for Data Access](queries-in-the-aot-for-data-access.md)

[Form Data Source Properties](form-data-source-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

