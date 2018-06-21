---
title: Query Record Retrieval Sequence
TOCTitle: Query Record Retrieval Sequence
ms:assetid: 88e2a8fc-6e3b-4806-9b12-5a8c2a0755dd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314836(v=AX.60)
ms:contentKeyID: 35246268
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Query Record Retrieval Sequence [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When a query is designed in the Application Object Tree (AOT), it can access data from [multiple data sources](how-to-add-multiple-data-sources-to-a-query.md). These data sources can be created at the same level as each other or nested in a parent-child relationship. The sequence of the retrieved records depends on how the data sources are linked.

## Outer Joins

If a single data source is nested as shown in the following figure and the JoinMode property is set to OuterJoin, the records are fetched in the following sequence:

  - A1, B1, A2, B2, A3, B3,…An, Bn

![Sequence record fetching - one nested data source](images/Bb314836.Axdvgus00000064(en-us,AX.60).gif "Sequence record fetching - one nested data source")

**A data source with a single child data source**

If more than one data source is nested, the child data sources are at the same level as shown in the following figure. The JoinMode property is set to OuterJoin, and the records are fetched in the following sequence:

A1, B1...Bn, C1…Cn, A2,…An, B1…Bn, C1…Cn

![Sequence record fetching - many nested datasources](images/Bb314836.Axdvgus00000063(en-us,AX.60).gif "Sequence record fetching - many nested datasources")

**A data source with multiple child data sources**

## Inner Joins

If nested data sources have an inner join, records are fetched in the following sequence:

  - A1, B1, C1, A2, B2,…An, Bn, Cn

## Exists Joins

If nested data sources have an exists join, records are only fetched from the primary data source as follows:

  - A1, A2, A3, A4…An

## See also

[How to: Add Multiple Data Sources to a Query](how-to-add-multiple-data-sources-to-a-query.md)

[Query Properties](https://msdn.microsoft.com/en-us/library/aa842737\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

