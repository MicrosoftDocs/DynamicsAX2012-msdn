---
title: Accessing Data
TOCTitle: Accessing Data
ms:assetid: 333a7cae-67ee-4929-927d-5d17f88a8c97
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa623755(v=AX.60)
ms:contentKeyID: 35241994
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Accessing Data [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Queries enable you to ask questions about the data in the Microsoft Dynamics AX database and retrieve information. There are two ways to create queries:

  - Use the **Queries** node in the Application Object Tree (AOT) to create static queries using a graphical interface. For more information, see [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md).

  - Use the query system classes to create dynamic queries in code. For more information, see [How to: Create Queries by Using X++](how-to-create-queries-by-using-x.md).

No matter which method that you use to create a query, the query can include a sorting order to sort the information that is returned. It can also include a range to filter the information that is returned based on your criteria.

A query can return data from multiple data sources. For more information, see [How to: Add Multiple Data Sources to a Query](how-to-add-multiple-data-sources-to-a-query.md).

You can create queries for forms and reports. For more information, see [How to: Coordinate Two Forms by Overriding an Event Method](how-to-coordinate-two-forms-by-overriding-an-event-method.md).

## Paging

When you create a query with X++, you can add paging support to that query. Paging retrieves the results of a query as a collection of one or more data subsets known as pages. The QueryRun class supports the following types of paging:

  - Position based paging divides the query result into pages and enables you to display the data records represented by a specified page.

  - Value based paging uses a page to represent the data records that are currently displayed in a data grid. Use value based paging when you want an update to a data grid to automatically redisplay the same set of data records.

To enable paging, use the enablePositionPaging and enableValueBasedPaging methods of the QueryRun class. To use paging with a query, the query cannot have a disabled data source. Also, the value of the FirstOnly property of the data source must be set to **No**.

## See also

[Customizing the Query Form](customizing-the-query-form.md)

[Query Properties](https://msdn.microsoft.com/en-us/library/aa842737\(v=ax.60\))

[Query System Classes](query-object-model.md)

[Using Expressions in Query Ranges](using-expressions-in-query-ranges.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

