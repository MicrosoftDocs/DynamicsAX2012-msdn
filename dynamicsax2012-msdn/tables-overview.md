---
title: Tables Overview
TOCTitle: Tables Overview
ms:assetid: 62b77e69-099b-439f-acee-b91729b2f0b5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314725(v=AX.60)
ms:contentKeyID: 35244600
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Tables Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Tables are the foundation objects in Microsoft Dynamics AX and store data used by the system. A table is made up of records (or rows) that contain information about a single entry in the table. For example, a specific customer or product. A record consists of one or more fields (or columns) that contain a discrete piece of data of a specific data type.

In Microsoft Dynamics AX, tables are located in the Application Object Tree (AOT) under the **Data Dictionary**\\**Tables** node. Each table contains the following primary elements:

  - Fields

  - Field Groups

  - Indexes

  - Relations

  - DeleteActions

  - Methods

A table name can contain letters and numbers but must begin with a letter. Spaces and special characters are not allowed. For more information about adding tables, see [How to: Create Tables](how-to-create-tables.md).

## Fields

The Fields node contains all the fields in the table. By specifying a field's data type, you define the type of data that can be stored in it. Microsoft Dynamics AX performs data validation to ensure that only valid data is entered into each field in the table. Constraints are also added to the database to set default field values if a field is left blank.

Each field in a table has a number of properties that describe the behavior of the field. The Type property contains the native data type of the field. The ExtendedDataType property contains the extended data type value (if the field is based on an extended data type). For more information about field properties, see [Table Field Properties](https://msdn.microsoft.com/en-us/library/aa577032\(v=ax.60\)).

### ![Bb314725.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314725.collapse_all(en-us,AX.60).gif")System Fields

When a new table is created, system fields are automatically added to each table. These fields are in the database table but aren't visible in the AOT **Fields** node. The system fields that are appended to a table depend on the value of particular table properties as shown in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>System field</p></th>
<th><p>Table property</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>Always</p></td>
</tr>
<tr class="even">
<td><p>RecVersion</p></td>
<td><p>Always</p></td>
</tr>
<tr class="odd">
<td><p>DataAreaId</p></td>
<td><p>SaveDataPerCompany = Yes</p></td>
</tr>
<tr class="even">
<td><p>CreatedBy</p></td>
<td><p>CreatedBy = Yes</p></td>
</tr>
<tr class="odd">
<td><p>CreatedDate</p></td>
<td><p>CreatedDate = Yes</p></td>
</tr>
<tr class="even">
<td><p>CreatedTime</p></td>
<td><p>CreatedTime = Yes</p></td>
</tr>
<tr class="odd">
<td><p>CreateTransactionId</p></td>
<td><p>CreateTransactionId = Yes</p></td>
</tr>
<tr class="even">
<td><p>ModifiedBy</p></td>
<td><p>ModifiedBy = Yes</p></td>
</tr>
<tr class="odd">
<td><p>ModifiedDate</p></td>
<td><p>ModifiedDate = Yes</p></td>
</tr>
<tr class="even">
<td><p>ModifiedTime</p></td>
<td><p>ModifiedTime = Yes</p></td>
</tr>
<tr class="odd">
<td><p>ModifiedTransactionId</p></td>
<td><p>ModifiedTransactionId = Yes</p></td>
</tr>
</tbody>
</table>


## Field Groups

Field groups are objects that group together fields that logically belong together. For more information about field groups, see [Best Practices for Field Groups](best-practices-for-field-groups.md), [Defining Field Groups](defining-field-groups.md),and [How to: Create a Field Group](how-to-create-a-field-group.md).

## Indexes

An index is a table-specific database structure that speeds the retrieval of rows from the table. Indexes are used to improve the performance of data retrieval and sometimes to ensure the existence of unique records. It's up to the database-specific query optimizer to use available indexes to facilitate efficient data retrieval.

The AllowDuplicates property on the index has the biggest impact on how the index is used. When set to No, the system creates a unique index on the specified fields in the database. Otherwise, a non-unique index is created. For more information about indexes and keys, see [Indexes Overview](indexes-overview.md).

### ![Bb314725.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314725.collapse_all(en-us,AX.60).gif")System Index

Microsoft Dynamics AX requires a unique index on each table. If there are no indexes on a table or all the indexes are disabled, a system index is automatically created. The system index is created on the RecId and DataAreaId fields if the DataAreaId field exists. Otherwise, the system index is created on the RecId field. You can see system indexes in the database, but they aren't visible in the AOT.

If there are indexes on a table but none of them are unique, the runtime estimates the average key length of the existing indexes, selects the index with the smallest key length, and then appends the RecId column to create a unique index.

## Relations

Relations define the relationship between two tables that contain related data. Table relations are used to enforce referential integrity among other functions.

Table relations are most commonly used in form fields to enable the look-up of information in another table. If a table relation exists, the **Lookup** button can be used to display a lookup list of values for a particular field. For more information about table relations, see [Defining Table Relations](defining-table-relations.md).

## DeleteActions

The DeleteAction element is used to maintain database consistency when a record is deleted. Define delete actions to specify what should occur when data being deleted in the current table is related to data in another table. The delete action values are None, Cascade, Restricted, and Cascade + Restricted. For more information about delete actions, see [Maintaining Data Integrity](maintaining-data-integrity.md) and [How to: Create Delete Actions](how-to-create-delete-actions.md).

## Methods

The **Methods** node displays all the methods available from a table. Use this node to add a new method, or override methods on the Table kernel class and add your own code.

### ![Bb314725.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314725.collapse_all(en-us,AX.60).gif")Add a New Method

1.  Browse to the **Data Dictionary**, **Tables** node in the AOT.

2.  Expand the table, right-click the **Methods** node, and then select **New Method**.

3.  Enter your code in the **Editor window** and save your changes.

### ![Bb314725.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb314725.collapse_all(en-us,AX.60).gif")Override a Method

1.  Browse to the **Data Dictionary**, **Tables** node in the AOT.

2.  Expand the table, right-click the **Methods** node, and then select **Override Method**.

3.  Select the method that you want to override.

4.  Enter your code in the **Editor window**, and then save your changes.

Methods that have been overridden display an icon with an arrow.

For more information about using methods in your tables, see [Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\)).

## Table properties

The table has a number of properties that define its behavior. For more information about customizing your tables, see [Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\)).

## See also

[How to: Create Tables](how-to-create-tables.md)

[Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\))

[Table Field Properties](https://msdn.microsoft.com/en-us/library/aa577032\(v=ax.60\))

[Primitive Data Types](primitive-data-types.md)

[Best Practices for Field Groups](best-practices-for-field-groups.md)

[Defining Field Groups](defining-field-groups.md)

[How to: Create a Field Group](how-to-create-a-field-group.md)

[Indexes Overview](indexes-overview.md)

[Defining Table Relations](defining-table-relations.md)

[Maintaining Data Integrity](maintaining-data-integrity.md)

[Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\))

[How to: Create Delete Actions](how-to-create-delete-actions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

