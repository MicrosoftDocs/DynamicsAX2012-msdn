---
title: 'Best Practice Performance Optimizations: AOS Tuning'
TOCTitle: 'Performance Optimizations: AOS Tuning'
ms:assetid: 8414aa72-03e7-4b40-8df9-758c71348897
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa643517(v=AX.60)
ms:contentKeyID: 35246161
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practice Performance Optimizations: AOS Tuning [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

"AOS tuning" is about minimizing the number of calls between the client and the server. The amount of data transported per call is not as important as the number of calls.

## Achieve the "select Discount"

Whenever a select statement is executed against a data source that is located on another tier, the number of records returned has a certain minimum size (it may return more records than requested). If more records are requested, a new call is performed, and another batch of records are returned for further processing. This effect is referred to as the "select discount", because a round trip to the server is not made for every record fetched, but only for every batch of records.

The "select discount" can be compared to how an insert or an update always cost one call per record.

If you know you only need one record, specify that by using the firstOnly select statement qualifier.

Normal tables have the data source located on the server. Temporary tables have their data source located at the tier where the code was running at the first call to insert.

## Use Containers to Reduce Client/Server Calls

Sometimes you want to transport the values of a large number of variables, or the result of lots of method calls from one tier to another. This costs a lot of client/server calls. The solution can be to use a container holding all the values, transmitted in one call.

Many classes have pack/unpack methods that can be used in such operations.

## See also

[Best Practices: Performance Optimizations](best-practices-performance-optimizations.md)

[Best Practice Performance Optimizations: General Programming](best-practice-performance-optimizations-general-programming.md)

[Best Practice Performance Optimizations: Database Design and Operations](best-practice-performance-optimizations-database-design-and-operations.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

