---
title: Indexes Overview
TOCTitle: Indexes Overview
ms:assetid: f81d39af-54d6-4c1f-bb48-2611668096a5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb278358(v=AX.60)
ms:contentKeyID: 35253640
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Indexes Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An index is a table-specific database structure that speeds the retrieval of rows from a table. Indexes are used to improve the performance of data retrieval and occasionally to ensure the existence of unique records. It's up to the database-specific query optimizer to use available indexes to facilitate efficient data retrieval.

Indexes are associated with a single table and located in the Application Object Tree (AOT) under the **Data Dictionary\\Tables** node underneath the specific table.

Like most database objects in Microsoft Dynamics AX, indexes are synchronized with the database. Once created, indexes are managed automatically by the DBMS every time a record is inserted, updated, or deleted. Within Microsoft Dynamics AX, an index can be enabled or disabled. When an index is disabled, it's deleted from the database and rebuilt if it's enabled later. For more information about creating an index, see [How to: Create an Index](how-to-create-an-index.md).

An index is defined by one or more fields. The system attempts to order the index according to the first field, and if there is more than one record with the same value in this field, the sorting conflict is resolved by looking at the next field and so on. When selecting table fields for an index consider the following:

  - Fields that are often searched by a range.

  - Fields that frequently participate in joins.

  - Fields that are frequently used to order or group a result set.

In theory, a table can have an unlimited number of indexes. However, it's common to have at most a few indexes enabled because every insert, update, and delete causes each index to be updated and can affect performance.

## Unique and Non-Unique Indexes

There are two types of indexes: unique and non-unique. Whether an index is unique is defined by the index's AllowDuplicates property. When this property is set to No, a unique index is created. The database uses the unique index to ensure that no duplicate key values occur. The database prevents you from inserting records with duplicate key values by rejecting the insert

Setting the index's AllowDuplicates property to Yes creates a non-unique index. These indexes allow you to enter duplicate values for the indexed fields and are used for performance reasons.


> [!NOTE]
> <P>A field of data type memo or container cannot be used in an index.</P>



### ![Bb278358.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb278358.collapse_all(en-us,AX.60).gif")System Index

Microsoft Dynamics AX requires a unique index on each table so if there are no indexes on a table or all the indexes are disabled, a system index is automatically created. The system index is created on the RecId and DataAreaId fields if the DataAreaId field exists. Otherwise the system index is created on the RecId field. You can see system indexes in the database but they aren't visible in the AOT.

If there are indexes on a table but none of them are unique, the runtime estimates the average key length of the existing indexes, chooses the index with the smallest key length and appends the RecId column to create a unique index.

## See also

[How to: Create an Index](how-to-create-an-index.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

