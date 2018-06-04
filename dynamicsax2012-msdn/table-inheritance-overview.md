---
title: Table Inheritance Overview
TOCTitle: Table Inheritance Overview
ms:assetid: cb4803e7-9a29-4c54-be43-63722557dac6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg881053(v=AX.60)
ms:contentKeyID: 35251435
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Table Inheritance Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A table can extend from or derive from another table. Each table has the **SupportInheritance** property and the **Extends** property, which together control table inheritance.

The default for each new table is to implicitly extend from the Common table. The extension from the Common table cannot be set or seen in the **Extends** property. A variable that is declared of a specific table also implicitly inherits methods from the xRecord class.

In the terminology for table inheritance, we say that the derived table extends its base table. But we never use the terms parent or child to explain tables in an inheritance relationship. The terms parent and child can be used to describe foreign key relationships between tables.


> [!IMPORTANT]
> <P>When you upgrade from Microsoft Dynamics AX 2009 to Microsoft Dynamics AX 2012, some tables are converted to use table inheritance. If you have customized those tables in Microsoft Dynamics AX 2009, the upgrade system is not able to upgrade those tables.</P>



## In This Section

  - [Inheritance Terminology](inheritance-terminology.md)

  - [When to Use Table Inheritance](when-to-use-table-inheritance.md)

  - [Walkthrough: Creating Base and Derived Tables](walkthrough-creating-base-and-derived-tables.md)

  - [Data Operations in X++ on Base and Derived Tables](data-operations-in-x-on-base-and-derived-tables.md)

  - [Selecting Data from a Table Inheritance Hierarchy](selecting-data-from-a-table-inheritance-hierarchy.md)

## See also

[Tables, Views, and Maps](tables-views-and-maps.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

