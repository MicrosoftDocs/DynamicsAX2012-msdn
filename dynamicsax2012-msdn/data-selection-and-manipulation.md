---
title: Data Selection and Manipulation
TOCTitle: Data Selection and Manipulation
ms:assetid: ead3caa2-1228-4ee4-b081-9377ed47ccb6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa883417(v=AX.60)
ms:contentKeyID: 35253234
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Data Selection and Manipulation [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use SQL statements either interactively or within source code, to access and retrieve data that is stored in the database. Data manipulation is performed through the following statements:

  - [insert](insert-table-method.md) adds one or more new records into a table.

  - [update](update-table-method.md) modifies data in existing table records.

  - [delete](delete-table-method.md) removes existing records from a table.

Before any data can be changed in Microsoft Dynamics AX, the data must first be selected for update by using a [select statement](select-statements.md). The select forUpdate command selects records exclusively for update.

The insert, update, and delete methods perform operations on only one record at a time. The [array insert](optimizing-record-inserts.md), [insert\_recordset](insert-recordset.md), [RecordInsertList](https://msdn.microsoft.com/en-us/library/gg923748\(v=ax.60\)), and [update\_recordset](update-recordset.md) statements perform operations on multiple records at a time.

## See also

[Maintain Fast SQL Operations](maintain-fast-sql-operations.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

