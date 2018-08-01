---
title: Maintaining Data Integrity
TOCTitle: Maintaining Data Integrity
ms:assetid: 6dc4ed0e-ebfd-41bb-875a-18eea23f455a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa672802(v=AX.60)
ms:contentKeyID: 35244813
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Maintaining Data Integrity [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can maintain database integrity by using one or more of the following features:

  - A DeleteAction element maintains database consistency when a record is deleted. For more information about adding a DeleteAction element, see [How to: Create Delete Actions](how-to-create-delete-actions.md).
    

    > [!NOTE]
    > <P>If you add a DeleteAction to a table and you use the delete_from statement, database performance will be slow. For more information, see <A href="delete-from.md">delete_from</A>.</P>



  - The forUpdate keyword in a select statement and the selectForUpdate table method ensure that records must be selected before they are updated or deleted. For more information, see [Select Statement Syntax](select-statement-syntax.md).

  - The ttsbegin, ttscommit, and ttsabort keywords ensure that all changes that are associated with a transaction are completed successfully. If the changes are not successfully completed, the transaction is aborted and the database is rolled back to the initial state.

  - The [UnitofWork](https://msdn.microsoft.com/en-us/library/gg958246\(v=ax.60\)) class can simplify the task of modifying the data records in multiple tables within the scope of a single transaction. For more information, see [How to: Use the UnitOfWork Class to Manage Database Transactions](how-to-use-the-unitofwork-class-to-manage-database-transactions.md).

## See also

[Database for Microsoft Dynamics AX](database-for-microsoft-dynamics-ax.md)

[Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\))

[How to: Create Delete Actions](how-to-create-delete-actions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

