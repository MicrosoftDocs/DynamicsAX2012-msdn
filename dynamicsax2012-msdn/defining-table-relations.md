---
title: Defining Table Relations
TOCTitle: Defining Table Relations
ms:assetid: 7ecbfc3c-b45e-4394-bf1a-20f49f498ef1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb190076(v=AX.60)
ms:contentKeyID: 35246127
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Defining Table Relations [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The foundation of Microsoft Dynamics AX is the relational database. Relationships can be created between tables that contain related data. In Microsoft Dynamics AX, the relationship between tables is called a relation.

Relations in Microsoft Dynamics AX:

  - Keep the database consistent (enforce referential integrity).

  - Are used by the Auto Join system in forms.

  - Enable the look up of values in other tables (through lookup list/selection list boxes and the **View details** Form command).

  - Are used to validate data.

  - Automatically propagate changes from one table to another.

  - Auto-define table relationships in queries.

Table relations are most commonly used in form fields to enable the look up of information in another table. If a table relation exists, the lookup button can be used to display a lookup list of values for a particular field.

A table relation is created by specifying one or more fields in a table that contain the same value in a related table. The matching fields typically have the same name in each table. For example, a SalesOrder table containing orders might have a field called SalespersonID, which identifies the salesperson that took the order. The Salesperson table, containing the names of sales people, would also have a field called SalespersonID. To create a table relation, specify that the SalesOrder.SalespersonID field is related to the Salesperson.SalespersonID field.

Table relationships are created, viewed, and edited in the Application Object Tree (AOT). When a table relation is created in Microsoft Dynamics AX, you must first specify the table involved in the relation and then define the fields in both tables that are related. For more information, see [How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md).

Conditional relationships can be created by adding a condition to a table relation. Only records that fulfill the condition are included in the relation. A condition on a relation filters the records on either the table that contains the relation or the related table, depending on the type of condition. For more information, see [Conditional Table Relations](conditional-table-relations.md).

## See also

[Best Practices for Table Relations](best-practices-for-table-relations.md)

[How to: Add a Relation to a Table](how-to-add-a-relation-to-a-table.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

