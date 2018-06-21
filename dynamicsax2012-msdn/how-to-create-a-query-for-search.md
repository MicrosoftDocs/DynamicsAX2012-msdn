---
title: 'How to: Create a Query for Search'
TOCTitle: 'How to: Create a Query for Search'
ms:assetid: 1cbf7ca3-c224-4a53-a6bd-d04bb1981491
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh397315(v=AX.60)
ms:contentKeyID: 36929806
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Query for Search [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To allow a table to be searched, you must create a query that is used to crawl the table data.

## Creating a Query for Search

You must create a query that provides access to the table you want to search. We recommend that you make a new query that is used only for search.

### To create a query for search

1.  In the AOT, expand the **Queries** node.

2.  Right-click the **Queries** node and then click **New Query**.

3.  Right-click the new query and then click **Properties**.

4.  Rename the query by modifying the **Name** property. We suggest using a name that indicates the query is to be used for search. For example, the query to search work orders in the Facility Management sample is named FCMWorkOrdersSearch.

5.  Set the **Title** property for the query to the name that identifies the type of data that will be returned from the search.

6.  Set the **Searchable** property to **Yes**.

7.  Save the changes in the AOT.

## Adding a Data Source to a Query

### To add a data source to a query

1.  In the AOT, expand the **Queries** node.

2.  Expand the node for the query that you are using for search.

3.  Right-click the **Data Sources** node and then click **New Data Source**.

4.  Right-click the new data source and then click **Properties**.

5.  Rename the data source by modifying the **Name** property. Use a name that indicates the table you are using for the data source.

6.  Set the **Table** property to indicate the table that you want to search.

7.  Expand the new data source and select the **Fields** node.

8.  Set the **Dynamic** property to **Yes**.

9.  Save the changes in the AOT.

Before you can use the new search query, you must restart the services that are used for search. See [Restarting Services for Search](restarting-services-for-search.md) for more information.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

