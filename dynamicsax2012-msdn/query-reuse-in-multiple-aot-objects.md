---
title: Query Reuse in Multiple AOT Objects
TOCTitle: Query Reuse in Multiple AOT Objects
ms:assetid: 555f4648-5f93-42e3-bbd1-77b83fd43c4e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc590130(v=AX.60)
ms:contentKeyID: 35244330
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Query Reuse in Multiple AOT Objects 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following Application Object Tree (AOT) object types can have a query as their data source:

  - **Data Sets**

  - **Forms**

  - **Reports**

  - **Views**

Under the **Data Sources** node of a **Form**, you can build a complex query that consists of multiple data sources. You can repeat this process for a **Report** and a **View**.

However, it is easier to build the business object structure one time by using the query framework, and then reuse the query. You can reuse the query as the data source for a form, report, and view.

## Query Changes are Instantly in Effect for Consuming Objects

A change to a query instantly goes into effect for all the forms, reports, and other AOT objects that use the query as their data source. This design avoids the labor and risk involved when the same table join must be modified repeatedly under the **Data Sources** node in several AOT objects.

## Query Cannot be Combined with Other Data Sources

When an AOT object has a query as its data source, no other item can be an additional data source. Therefore no table, view, or any other query can be added to a **Data Sources** node that already has a query.

## See also

[Query Framework in the AOT](query-framework-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

