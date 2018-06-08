---
title: Queries Best Practices
TOCTitle: Queries
ms:assetid: d29e14e9-2190-44f1-87b3-d7a21da0d478
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa872046(v=AX.60)
ms:contentKeyID: 35251938
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Queries Best Practices 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Queries can be seen as a class interface for creating select statements.

Use a query in place of a select statement when the structure of the "select" (query) is not known until run time, or when the user should be able to specify the ranges. In other situations, use a select statement. Select statements are often easier to read, and they are much more compile-time stable.

Queries are embedded in Forms, Reports and RunBase jobs and should always be used with these application objects, unless there are good reasons not to.

Queries are very flexible. Everything can be specified at run time, but specify as much as possible before run time.

Create queries in the Application Object Tree (AOT) where possible, instead of building them in code.

Use [intrinsic functions](intrinsic-functions.md) everywhere possible to enable compile-time checking of code.

The range of a query can be specified under program control by using two different techniques, the normal one and the query range value expression. Both take a string as an argument that is not evaluated until run time. The string must fulfill certain syntax restrictions and be as compile-time stable as possible.

## Normal Query Range Values

Always use the SysQuery::value method when you are programmatically assigning an atomic value to a query range.

Always use the SysQuery::range method when you are programmatically assigning a value range to a query range. The range method will supply the needed ".." operators.

Always use the SysQuery::valueEmptyString method when you want to have a range which must have a blank value.

Always use the SysQuery::valueUnlimited method when you want to have a completely open range.

## Query Range Value Expressions

Only use the [query range value expressions](using-expressions-in-query-ranges.md) if the normal query range values cannot be used.

Be aware that query range value expressions are evaluated only at run time (so they are not checked at compile time).

Because the contents of the Query range value expressions should look like X++, you should be careful to format the different data types correctly. Use the strFmt system function or queryValue/queryRange for this. queryValue and queryRange are methods on the Global class.

Place the expression in a range that is defined on the most relevant of the involved fields.

## See also

[X++ Standards: select Statements](x-standards-select-statements.md)

[Using Expressions in Query Ranges](using-expressions-in-query-ranges.md)

[Query Object Model](query-object-model.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

