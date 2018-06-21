---
title: Select Statements
TOCTitle: Select Statements
ms:assetid: 9a6111f0-f4d2-4b67-ba8f-9f7298ae2a4d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa845764(v=AX.60)
ms:contentKeyID: 35248136
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Select Statements [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The select statement fetches or manipulates data from the database or both fetches and manipulates data from the database.

All select statements use a table variable to fetch records. This variable must be declared before a select statement can be executed.

The select statement only fetches one record, or field. To fetch additional records, you can use the next statement. The next statement fetches the next record in the table. If you use next without a preceding select command, an error occurs. Do not use next with the firstOnly find option. If you need to traverse a number of records, it is more appropriate to use a while select statement.

Results of a select statement are returned in a table buffer variable. If you use a field list in the select statement, only those fields are available in the table variable. If you use aggregate functions, such as sum or count, the results are returned in the fields that you perform the sum or count over. You can only count, average, or sum the integer and real fields.

## See also

[Select Statement Examples](select-statement-examples.md)

[Select Statement Syntax](select-statement-syntax.md)

[Select Statements on Fields](select-statements-on-fields.md)

[while select Statements](while-select-statements.md)

[X++ Standards: select Statements](x-standards-select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

