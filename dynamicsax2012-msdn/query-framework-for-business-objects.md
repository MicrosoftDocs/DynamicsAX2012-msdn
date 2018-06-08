---
title: Query Framework for Business Objects
TOCTitle: Query Framework for Business Objects
ms:assetid: f27a27b7-8ee2-45b0-9712-641d404ec68a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc642177(v=AX.60)
ms:contentKeyID: 35253414
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Query Framework for Business Objects 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the Application Object Tree (AOT), the query object can be designed as a modular business object. The following AOT object types could have their **Data Sources** node be based on a query object:

  - **Data Sets**

  - **Forms**

  - **Reports**

  - **Views**

## Object Reuse

A query that is developed as a business object (such as for sales order) can be used to build AOT objects, such as a report. The benefits of object reuse include the following:

  - There is less AOT work for you in building data sources.

  - You have to make data source changes in only one query. This causes fewer errors than when you must modify several objects the same way.

  - The changes that you make to the one query are instantly in effect for all objects based on that query.

### ![Cc642177.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc642177.collapse_all(en-us,AX.60).gif")Ways to Reuse a Query

Three ways a query can be reused include:

  - [Query Reuse in Multiple AOT Objects](query-reuse-in-multiple-aot-objects.md)

  - [Query Reuse by Independent Duplication](query-reuse-by-independent-duplication.md)

  - [Query Reuse in Multiple AOT Objects](query-reuse-in-multiple-aot-objects.md)

For more information about how to design by using a composite query, see [Walkthrough: Creating a Form Based on a Composite Query](walkthrough-creating-a-form-based-on-a-composite-query.md).

## Alternative Designs

It is possible to rebuild a complex query in a data set, a form, a report, and then in a view. But the AOT supports data query designs that are almost as powerful as what the SQL select statement can do natively in the database products. So a better design is to consider building a query business object one time. Then you can reuse that query object in all the form and report objects that need the same data.

## See also

[Query Framework in the AOT](query-framework-in-the-aot.md)

[Forms in Microsoft Dynamics AX](forms-in-microsoft-dynamics-ax.md)

[View Basics](view-basics.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

