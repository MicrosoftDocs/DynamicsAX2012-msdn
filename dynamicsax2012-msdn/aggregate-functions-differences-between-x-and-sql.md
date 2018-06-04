---
title: 'Aggregate Functions: Differences Between X++ and SQL'
TOCTitle: 'Aggregate Functions: Differences Between X++ and SQL'
ms:assetid: 85ec9efe-9dbd-4a1e-b399-9cf32104ac2f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa677419(v=AX.60)
ms:contentKeyID: 35246199
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Aggregate Functions: Differences Between X++ and SQL 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In industry standard SQL, a database query can contain aggregate functions. Examples of such functions include count(RecID) or sum(columnA). When an aggregate function is used but no rows match the where clause, a row must be returned to hold the result of the aggregates. The one returned row shows the value 0 (zero) for the count function, and shows null for the sum function.

Microsoft Dynamics AX does not support the concept of null values for the database. Therefore, when the sum function would return null, no row is returned to the user. Also, each data type has a specific value that is treated like a null value in certain circumstances. For more information, see [Null Values for Data Types](null-values-for-data-types.md).

## See also

[Select Statements](select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

