---
title: Searching for Records Design Pattern
TOCTitle: Searching for Records
ms:assetid: 8a09bf1e-e0d8-4a0c-9bf2-99e2cfa6474b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa659249(v=AX.60)
ms:contentKeyID: 35246329
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Searching for Records Design Pattern [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The main techniques for selecting records in the database are as follows:

  - The select statement

  - A query

The techniques are essentially the same. They both deliver a set of records from the database in a table variable that can be accessed.

Use the select statement when:

  - The selection criteria are complex.

  - You are selecting a set of records from X++. The user is not going to change the selection criteria.

Use a query when:

  - The user can choose which records are selected.

  - The user can change the range of records to be selected.

  - The selection criteria are not more complex than the query can accommodate.

  - When you use queries, develop them in the Application Object Tree (AOT) or build them from scratch in your code. In both situations, the query can be modified in the code. A query built from scratch in code can be saved so that it occurs in the AOT. However, this should usually be avoided.

Build a query in the AOT when:

  - A specific query definition is being used in many places. (The query in the AOT can be reused.)

  - The query must contain code.

  - The query definition is more complex. The AOT provides a visual representation of the query.

## Using find

In the standard Microsoft Dynamics AX application, all tables with a unique key have a static find method. The arguments to the method correspond to the fields that make up the key. The return value is a table variable with the same data type as the table.

Implement and use find methods on your own tables. For more information, see [static find Method Design Pattern](static-find-method-design-pattern.md).

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

[Select Statements](select-statements.md)

[How to: Create Queries by Using X++](how-to-create-queries-by-using-x.md)

[Accessing Data](accessing-data.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

