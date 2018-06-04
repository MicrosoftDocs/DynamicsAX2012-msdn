---
title: Map Overview
TOCTitle: Map Overview
ms:assetid: ca5acde8-10de-426d-af91-ef13dbbe74d6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb278211(v=AX.60)
ms:contentKeyID: 35251271
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Map Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Maps define X++ elements that wrap table objects at run time. With a map, you associate a map field with a field in one or more tables. This enables you to use the same field name to access fields with different names in different tables. Map methods enable you to create or modify methods that act on the map fields.

A table can be accessed through more than one map. Typically, if more than one map accesses the same table, each map accesses different subsets of fields in the table. Maps don't define database objects and so they aren't synchronized with the database. For more information about creating maps, see [How to: Create Maps](how-to-create-maps.md).

## Benefits

The benefits of maps include:

  - Simplicity - maps provide a single interface to fields in multiple tables. This means that any object referencing the map field can be used against multiple tables without changing any field names.

  - Consistency - table fields with varying names can be accessed in code in a consistent manner. For example by using a map, fields named Zip in one table, ZipCode in another, and PostalCode in yet another table can all be accessed by the name ZipCode.

  - Code reuse - a map method enables you to add code that runs against the map fields. A single map method prevents the duplication of methods and code on each table.

## Map Elements

In Microsoft Dynamics AX, maps are located in the Application Object Tree (AOT) under the **Data Dictionary** \> **Maps** node. Each map has four primary elements:

  - Fields

  - Field Groups

  - Mappings

  - Methods

### ![Bb278211.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278211.collapse_all(en-us,AX.60).gif")Fields

The **Fields** node contains the map field elements. Each field must be the same data type as the field to which it's associated. Use the ExtendedDataType property to specify the map field's data type if the map field is associated with a table field that's based on an extended data type.

### ![Bb278211.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278211.collapse_all(en-us,AX.60).gif")Field Groups

The **Field Groups** node contains field groups that group together fields that logically belong together. Field groups in maps work the same way they do in tables. For more information about field groups, see [Best Practices for Field Groups](best-practices-for-field-groups.md), [Defining Field Groups](defining-field-groups.md), and [How to: Create a Field Group](how-to-create-a-field-group.md).

### ![Bb278211.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278211.collapse_all(en-us,AX.60).gif")Mappings

The **Mappings** node is where the map fields are associated with table fields. Directly under the **Mappings** node are the tables that the map combines. Under each table you can see which table field is associated to which map field. If a field exists in the map with no associated field in a particular table, just leave the MapFieldTo property blank.

### ![Bb278211.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278211.collapse_all(en-us,AX.60).gif")Methods

The **Methods** node displays all the methods available from a map. In this node you can add a new method or you can override methods on the xRecord kernel class and add your own code.

## See also

[How to: Create Maps](how-to-create-maps.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

