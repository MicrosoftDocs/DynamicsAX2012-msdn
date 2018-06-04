---
title: Record Caching
TOCTitle: Record Caching
ms:assetid: d2270c57-5c66-4045-bbeb-83a1d21d7def
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb278240(v=AX.60)
ms:contentKeyID: 35251881
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Record Caching 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX database record caching is a performance-enhancing feature that helps avoid database access when it's not strictly necessary. Retrieving database records from memory instead of the database significantly speeds up data access. Caching can reduce the performance penalty for repetitively accessing the same database records.

## Types of Caching

Caching is transparent to the application; however, it's important to know how caching works to optimize its performance in Microsoft Dynamics AX. Following are the types of caching:

  - Single-record

  - Set-based

Single-record caching has the following characteristics:

  - Defined at design time

  - Moves records to the cache based on the table's CacheLookup property and the type of SELECT statement that is used to retrieve the record

For more information about record caching, see [Single-record Caching](single-record-caching.md).

Set-based caching has the following characteristics:

  - Defined either at design time or in X++ code

  - Moves sets of records to the cache

  - Implemented either through the table's CacheLookup property or in code by using the RecordViewCache class

For more information about caching sets of records, see [Set-based Caching](set-based-caching.md).

## See also

[Single-record Caching](single-record-caching.md)

[Set-based Caching](set-based-caching.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

